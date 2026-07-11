---
resource_type: Audio QC Standard (通用)
project: haevo-records
applicable_to: 所有 Track 母带 (Track 1-N, 任何 Artist)
version: v1.0
status: LOCKED (Permanent Rule, Slow Evolution)
last_updated: 2026-07-11
confidence: ★★★★ (4 Spotify/Apple/YouTube/Sleep 平台官方标准综合 + 3 个母带实战验证)
next_review: 2026-10-11 (季度 Review)
---

# Haevo Records — 母带音频 QC 通用标准 v1.0

> **目的**: 为 Haevo Records 旗下所有 Track 母带 (任何 Artist, 任何路由) 提供**统一、可执行、可脚本化**的质量检测标准。本文件**不针对任何具体 Track**, 通用规则永久适用, Slow Evolution (季度 Review)。

---

## 0. 使用方式

### 0.1 何时跑 QC?
- **D4 母带锁定后** (Playbook D4 节点)
- **D6 平台提交前** (Playbook D6 节点, 最终把关)
- **T+0 发布后** (存档备查, 不修改)

### 0.2 怎么跑?
- **手动**: 按本文件 § 1-8 检测项逐项执行命令
- **脚本自动化**: `track-qc-check.py <file.flac> --route <spotify|youtube|sleep>` (在 `bot-b/scripts/`)

### 0.3 路由分档 (Route-Specific Targets)

不同发行路由的母带目标**不同**, 跑 QC 前先选定路由:

| 路由 | 时长目标 | Loudness (LUFS) | True Peak (dBTP) | LRA (LU) | 备注 |
|---|---|---|---|---|---|
| **Spotify / Apple Music** (Pop 单曲) | 4-6 min | **-14.0 ±1.0** | **-1.0** | 7-12 | Spotify 推荐 -14, Apple Music 推荐 -16 |
| **YouTube** (Ambient / Sleep 长篇) | 10 min - 1 hr | **-16.0 ±1.0** | **-1.0** | 8-14 | YouTube 自动 normalize 到 -14, 但母带 -16 更稳 |
| **Sleep 30min+** (Sleep / Meditation) | 30 min - 8 hr | **-18.0 ±2.0** | **-2.0** | 10-20 | 平台自动大幅降噪, 母带留足余量 |

> **默认**: 选 `spotify` (Haevo Records 主发行路由)

---

## 1. 容器完整性 (Container Integrity) — 必检

| # | 检测项 | 工具 | 命令模板 | 合格标准 |
|---|---|---|---|---|
| 1.1 | 编码格式 | `ffprobe` | `ffprobe -show_streams FILE \| grep codec_name` | **FLAC** (lossless) |
| 1.2 | 采样率 | `ffprobe` | `ffprobe -show_streams FILE \| grep sample_rate` | **44100** (CD 级) |
| 1.3 | 位深 | `ffprobe` | `ffprobe -show_streams FILE \| grep bits_per_raw_sample` | **16** (CD 级, 非 0) |
| 1.4 | 声道数 | `ffprobe` | `ffprobe -show_streams FILE \| grep channels` | **1 (mono)** 或 **2 (stereo)**, 依 Track 类型 |

**失败处理**: 1.1-1.3 任一 FAIL = 重跑母带 (不是修了, 是源头错)。

---

## 2. 时长 + 文件大小 — 必检

| # | 检测项 | 工具 | 命令模板 | 合格标准 |
|---|---|---|---|---|
| 2.1 | 时长精确度 | `ffprobe` | `ffprobe -show_format FILE \| grep duration` | 误差 **≤ 0.5s** vs 母带目标时长 |
| 2.2 | 时长合理性 | 人工判断 | 看 § 0.3 路由分档 | 符合所选路由时长目标 |
| 2.3 | 文件大小 | `ls -la` | `ls -la FILE` | **24MB ± 30%** (4min FLAC, 实际因路由变化) |
| 2.4 | FLAC probe 评分 | `ffprobe` | `ffprobe -show_format FILE \| grep probe_score` | **100** (FLAC 满分) |

**失败处理**: 2.1 误差 > 0.5s = 检查 fade-out 时长; 2.4 < 100 = FLAC 文件损坏, 重跑。

---

## 3. Loudness 母带规格 — 必检 (核心)

| # | 检测项 | 工具 | 命令模板 | 合格标准 |
|---|---|---|---|---|
| 3.1 | Integrated Loudness | `ffmpeg loudnorm` | `ffmpeg -i FILE -af loudnorm=I=TARGET:TP=TARGET_TP:LRA=11:print_format=summary -f null -` | **±1.0 LUFS** of route target (见 § 0.3) |
| 3.2 | True Peak | `ffmpeg loudnorm` 或 `ebur128=peak=true` | `ffmpeg -i FILE -af ebur128=peak=true -f null -` | **≤ route target TP** (见 § 0.3) |
| 3.3 | Loudness Range | `ffmpeg loudnorm` | 同 3.1 命令 | **在路由 LRA 区间内** (见 § 0.3) |
| 3.4 | Target Offset (双 pass) | `ffmpeg loudnorm` 2-pass | 跑 2 次 loudnorm, 比较 offset | **≤ 0.5 LU** (达标) |

**母带 SOP**: `2-pass loudnorm` (EBU R128 K-weighting + dual-gate) + 末尾 `afade=t=out:st=X:d=4` (4s 淡出)

**失败处理**: 3.1 偏离 > 1 LUFS = 重跑 loudnorm 第 2 pass; 3.2 > target TP = 用 limiter 重压。

---

## 4. 频谱 + 动态 — 推荐检

| # | 检测项 | 工具 | 命令模板 | 合格标准 |
|---|---|---|---|---|
| 4.1 | DC Offset | `ffmpeg astats` | `ffmpeg -i FILE -af "astats=metadata=1:reset=1" -f null -` | **0 ±0.001** (避免低频污染) |
| 4.2 | Peak Level | `ffmpeg astats` | 同 4.1 命令, 看 `Peak level dB` | **≥ -3 dBFS** (有动态余量) |
| 4.3 | RMS Level | `ffmpeg astats` | 同 4.1 命令, 看 `RMS level dB` | **依路由** (Spotify -20~-16 / Sleep -25~-20) |
| 4.4 | 静音检测 | `ffmpeg silencedetect` | `ffmpeg -i FILE -af silencedetect=noise=-50dB:d=2 -f null -` | 整段 **≤ 0.5s** 静音 (除末尾淡出) |

**失败处理**: 4.1 DC offset > 0.001 = 高通滤波 20Hz 修; 4.4 长静音 = 检查 fade-in/out。

---

## 5. 元数据完整性 — 必检

| # | 检测项 | 工具 | 命令模板 | 合格标准 |
|---|---|---|---|---|
| 5.1 | TAG 总数 | `metaflac --list` | `metaflac --list FILE \| grep "type: 4" -A 50` | **VORBIS_COMMENT** 至少 **5+ comment** (TITLE/ARTIST/ALBUM/GENRE/LYRICS) |
| 5.2 | PICTURE block | `metaflac --list` | `metaflac --list FILE \| grep PICTURE` | **1 张 cover** (3000x3000 PNG/JPG) |
| 5.3 | 编码器版本 | `metaflac --list` | 看 `vendor string` | **Lavf60+** (FFmpeg ≥ 4.0) 或 `reference libFLAC` |
| 5.4 | STREAMINFO MD5 | `metaflac --list` | 看 STREAMINFO 内嵌 MD5 | **记录** (无损传输验证) |
| 5.5 | 文件 MD5 | `md5sum` | `md5sum FILE` | **记录** (交付验证) |

**必备 tags 清单** (Haevo Records 标准):
- TITLE (Track 名, 中英)
- ARTIST (含中文别名)
- ALBUM (单曲 = Track 名)
- GENRE (RouteNote 39-list 主 Genre)
- SUBGENRE (Brand DNA sub-tags)
- LYRICS (完整歌词, 简繁主副)
- LANGUAGE (主 + 副, IETF 格式如 zh-Hant)
- COMPOSER / LYRICIST / PRODUCER (创作者全名)
- LABEL (Haevo Records)
- AI_DISCLOSURE (AI 生成声明)
- DATE (Release Date YYYY-MM-DD)
- ISRC (12 字符)
- UPC (13 位 EAN-13, 单曲可空)

**失败处理**: 5.1 tags 缺失 = 用 `metaflac --set TAG=VALUE` 补; 5.2 PICTURE 缺失 = `metaflac --import-picture-from`。

---

## 6. 听感 + AI 污染 — 必检 (Suno / Udio 特有)

| # | 检测项 | 工具 | 命令模板 | 合格标准 |
|---|---|---|---|---|
| 6.1 | 0-30s Suno 水印 | Whisper + 人工 | `whisper FILE --model small` | **无** "作曲/作词/Suno" 等词 |
| 6.2 | Double 复读 | Whisper multi-window + 人工 | 同 6.1, 但跑多个窗口 | **无** 同段 ≥ 2 词重复 |
| 6.3 | 中文字错率 | Whisper transcript 字符对比 | 同 6.1 | **< 30%** (Suno 中文训练集缺陷下限) |
| 6.4 | Brand DNA 对位 | 人工听感 vs Brand Bible | 听 Track, 对照对应 Artist DNA 章节 | **5/5 元素对位** (月/雾/风/烟/山水灯雁等) |

**失败处理**: 6.1 有水印 = 选其他 A 段 (Suno A1-A4 多跑选); 6.2 double = 选其他 A 段; 6.4 偏离 = 重写 Suno Prompt。

---

## 7. 平台分发 — 提交前必检

| # | 检测项 | 工具 | 合格标准 |
|---|---|---|---|
| 7.1 | UPC (EAN-13) | RouteNote / DistroKid dashboard | **13 位数字**, 自动分配或自有 |
| 7.2 | ISRC (12 字符) | RouteNote / DistroKid dashboard | **CC-XXX-YY-NNNNN** (RouteNote 自签 OK) |
| 7.3 | Genre 对位 | Brand Bible + 平台实测 | 符合 Artist Brand DNA § Genre |
| 7.4 | Release Date | 平台提交表单 | 符合 Playbook T-0 时点 |
| 7.5 | Cover 分辨率 | 平台提交表单 | **3000x3000 px** (Spotify 最低 3000) |

---

## 8. 文件传输 — 交付前必检

| # | 检测项 | 工具 | 合格标准 |
|---|---|---|---|
| 8.1 | 传输方式 | 看交付记录 | **不走 Telegram** (≥20MB FLAC Telegram 重编码丢 meta) |
| 8.2 | 跨平台 md5 一致 | 用户端 `md5sum` | **匹配 VPS md5** (无损传输验证) |
| 8.3 | git push 状态 | `git log --oneline -1` | **HEAD 含最新 commit** |

**推荐传输方式** (按优先级):
1. **Git LFS** (HKYOB 私库, 永久)
2. **mega.nz** (用户偏好, megatools 可用)
3. **GitHub Release** (公开/私有, 永久)
4. **litterbox.catbox.moe** (72h 临时)
5. ❌ **Telegram** (≥20MB FLAC 禁用)

---

## 9. 综合评分阈值 (Ship Gate)

| 总分区间 | 状态 | 行动 |
|---|---|---|
| **≥ 90%** | ✅ LOCKED | 可提交平台, 进 D6 |
| **85-89%** | ⚠️ MINOR FIX | 修小瑕疵 (非阻塞), 可提交 |
| **70-84%** | ❌ MAJOR FIX | 必须修, 重跑 QC |
| **< 70%** | ❌❌ REJECT | 重做母带 |

> 各检测项权重见 `track-qc-check.py` 脚本配置。

---

## 10. 已知 Limitation

1. **astats 数值偶尔 -inf**: 因 ffmpeg 版本差异, 4.2/4.3 可能输出 `-inf`, 此时**跳过**该项不扣分。
2. **Whisper 假阳性 double**: multi-window 把同一段分到多个时间戳 = 假阳性, 需人工确认。
3. **Suno 中文 vocal 字错率**: 平台缺陷, < 30% 已是下限, 不强求 0%。

---

## 11. 引用

- Spotify Master Guidelines: https://artists.spotify.com/ (Loudness -14 LUFS 推荐)
- Apple Music Master Guidelines: https://help.applemusic.com/ (Loudness -16 LUFS 推荐)
- YouTube Audio Guidelines: https://support.google.com/youtube/answer/4603579
- EBU R128 Loudness: https://tech.ebu.ch/publications/ebu_r128
- Haevo Records Brand DNA (各 Artist)

---

## 12. AI Update Log

| 日期 | 事件 |
|---|---|
| 2026-07-11 | v1.0 首版, 3 路由分档 (Spotify/YouTube/Sleep), 8 大类 27 项检测 |
| 2026-07-11 | track-qc-check.py 脚本创建 (参数化: 文件 + 路由) |
| 2026-Q4 (待) | 第一次季度 Review, 收集 5+ Track 数据后调阈值 |

---

**标准版本**: v1.0 LOCKED
**下次 Review**: 2026-10-11 (季度)
**责任人**: bot-b (自动跑) + Kieran (人工听感 + Brand DNA 对位)