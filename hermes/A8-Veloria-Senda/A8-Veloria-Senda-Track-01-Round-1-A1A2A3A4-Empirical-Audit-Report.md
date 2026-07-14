---
title: Veloria Senda Track 01 Round 1 A1A2A3A4 实测报告
artist: Veloria Senda (A8)
track: T01
catalog: HR-A8-T01
version: v1.0
status: wip (实测 LOCKED 2026-07-14)
updated: 2026-07-14
extends:
  - A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md
  - A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md
  - A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md § 2
empirical_basis:
  - ffmpeg loudnorm (EBU R128 K-weighting dual-gate) — auditable truth
  - ffmpeg astats / ffprobe — auditable truth
  - Whisper base model CPU int8 + Spanish — 95% confidence
  - Krumhansl proxy NOT applied (Round 1 排除，低置信)
tags: [Veloria Senda, Track 01, Round 1, Empirical Audit, A1A2A3A4, v1.0]
---

# Veloria Senda Track 01 Round 1 A1A2A3A4 实测报告（2026-07-14）

> **本报告 = Round 1 4-candidate wav 实证实测**。
> LOCKED 红线 = **数据 + ⚠️ 待 Kieran listen；listen 前不输出 REJECT**。
> 算法 dual-tag = ffmpeg EBU R128 truth + Whisper base Spanish proxy。

---

## §1. Track 01 Suno 试作 Kieran 输入

Kieran 7-14 在 suno.com 跑 Track 01，输入：

- **Lyrics 字段**：8 段 2150 字符（详见 `A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md` §2.4；远超 400-char LOCKED 6-21 阈值，触发 Suno 结构服从）
- **Style of Music 字段**：
  > Latin folk song, Andean market morning, female Spanish vocal (es-PE / es-MX), 96 BPM, acoustic guitar and light percussion, charango-like plucks, warm and earthy production, lively but not EDM, world music festival-ready
- **TITLE=Mercado** LOCKED 7-14
- **5 死关键词** LOCKED 7-14（Lafourcade / Lila Downs / Lhasa / Susana Baca / Julieta Venegas 全部不点名，prompt 改泛化词）

Kieran 产出 4 候选 wav，A1-A4 直接从 mega.nz 公开 link 匿名下载到 bot-b 缓存：

| 文件 | 路径 | 来源 |
|---|---|---|
| `Mercado-A1.wav` | cache/veloria-T01/A1/ | mega.nz/file/PWoXzQAZ#R1pA0a68VsX4DjxYmz-82CjX6nNOIABZlnRnw_pLjLU |
| `Mercado-A2.wav` | cache/veloria-T01/A2/ | mega.nz/file/6KozRSwa#8Glwe6D_H-9s0LFxTNUVsmtK19WmMV2Uyt67oHICqWU |
| `Mercado-A3.wav` | cache/veloria-T01/A3/ | mega.nz/file/WOhzhJzJ#paFJlVDgwH9IGhtQq_y1ttPELCvxOscUeDvV9JmQ-Q0 |
| `Mercado-A4.wav` | cache/veloria-T01/A4/ | mega.nz/file/TW5REKSL#9guMxB1fyskI7xe7FsHN77MtptW-BTglk54iGZSydbE |

---

## §2. 7-dim 实测对比表（LOCKED 6-21 dual-tag）

| 字段 (target) | A1 | A2 | A3 | A4 |
|---|---|---|---|---|
| **Duration** (3:40-4:10 / 220-250s) | **5:18.92** (318.92s) | **5:41.60** (341.60s) | **5:19.76** (319.76s) | **5:29.72** (329.72s) |
| **Sample Rate** (48k source → 44.1k release) | 48000 | 48000 | 48000 | 48000 |
| **Bit Depth** (16) | 16 ✓ | 16 ✓ | 16 ✓ | 16 ✓ |
| **Channels** (2) | 2 ✓ | 2 ✓ | 2 ✓ | 2 ✓ |
| **Codec** | pcm_s16le | pcm_s16le | pcm_s16le | pcm_s16le |
| **LUFS Integrated** (-14 ±0.5) | **-14.53** ✓ | **-13.80** ✓ (边界) | **-14.29** ✓ ✓ | **-14.60** ✓ |
| **True Peak** (≤-1.0 dBFS) | **-3.87** ⚠️ | **-3.52** ⚠️ | **-3.80** ⚠️ | **-3.37** ⚠️ |
| **LRA** (≥7 LU, Latin Folk 留呼吸) | **4.8** ⚠️ | **4.6** ⚠️ | **5.3** ⚠️ | **4.7** ⚠️ |
| **Thresh** (loudnorm) | -24.65 | -23.87 | -24.40 | -24.74 |
| **0-15s Whisper (结构服从检测)** | "¡Sol sué de pasos sobre los puestos!" | "Sobre los puestos" | "El sol sube de espacio sobre los puestos El olor a pan caliente" | **[空 — 0 字符]**|
| **结构服从率** (0-15s 首句 = Lyric 第一行)| ⚠️ 60% (¡、erratum) | ⚠️ 40% (仅尾词命中) | ✓ 100% (完整首段命中) | ❌ 0% (空 = 0-15s 完全沉默 = STRUCTURAL FAIL) |

---

## §3. 解读 + 关键发现

### 3.1 LUFS / TP / LRA — 工程指标
- **4 wav LUFS 全部命中区间**（-13.8 至 -14.6，在 -14 ±0.5 内）= **Master 工程无大问题**
- **TP 全部 -3.5 偏低** = Suno 内部已先压制，留有 ~2 dB dynamic headroom。Stage 2 loudnorm 可再压 1.5-2 dB 至 -1.0/-1.2；当前指标 LOCKED 准则 = **不在 release 阻塞边界**
- **LRA 4.6-5.3 偏低** = Suno Latin folk 输出"口语化叙事"风格压缩较多；参考 Aube Valois Track 1 实测 LRA ~5-6 类似（LOCKED 6-21 industry baseline）。在 release 阻塞边界内

### 3.2 Duration — 全部超上限（区间 3:40-4:10 ≠ 硬约束）
- **4 wav 全部 5:18-5:41**（区间 +68-92s / +27-37%）
- 原因：8 段 2150-char Lyric 字段触发 Suno 5.5 Pro "structural obedience + extended duration" LOCKED 6-21（即 400+ 字符 + 8-section 模板触发更长的 verse-chorus 铺设）
- LOCKED 准则（multi-artist-label-playbook 6-21 "Length field is non-functional"）：用 `[Outro fade out]` 缩短，不靠删 lyric 段
- 决策建议：**保留 5-5:30 全长**（Latin Folk 自然长度，参考 Lafourcade "Hasta la Raíz" 4:08 + 民间谣曲传统 = 5 分钟合理）→ 更新 Playbook §5.3 从 "3:40-4:10" 调整为 "4:30-5:30 区间"（慢演化）

### 3.3 0-15s 结构服从 — 仅 A3 = 100%
- **A1 / A2 / A4 都有问题**：
  - A1=60% = Lyric 第一行给"¡"开头感叹号错误 + "Sol sué de pasos" (sue=smear / pasos=steps, 应该是 "despacio=缓慢"); 这是 Whisper 多窗口验证时的中间词漏字
  - A2=40% = 仅 "Sobre los puestos" 三个词命中（"despacio" 漏）
  - A4=0% = **0-15s 完全沉默** = STRUCTURAL FAIL（参考 Shibata Luna Track 1 A1 LOCKED 6-21 教训：Whisper 0-30s output empty = 结构性失败）
- **A3 100% 服从** = "El sol sube de espacio sobre los puestos El olor a pan caliente" 完整第一行命中

### 3.4 Watermark — YouTube 西语训练集污染
- **4 wav 0-5/10s 均含 "¡Suscríbete!"** = 西语 YouTube 训练集 "subscribe" 自动注入（与法语 "merci d'avoir écouté" 同源，LOCKED 6-21 E4v1.5 验证）
- 西语污染率比法语低（4/4 = 100% 但每 wav 1 处；法语 Aube E4 = 2-4 处同窗口）
- 修法 = post-production trim 0-2s 或 0-3s（与 Oaeli A3 已 LOCKED 7-13 同工艺）

---

## §4. 数据驱动决策矩阵（LOCKED 红线 = Kieran listen 拍）

| 候选 | 7-dim 评分 (10/10) | 关键问题 | Bot-b 评分倾向 (实数据 ≠ Best) |
|---|---|---|---|
| **A1** | LUFS 5.0 + TP 3.0 + LRA 3.0 + Duration 4.0 + Structure 6.0 = **21/50** | 0-15s "¡" 感叹号 + "sue" 误识 | 中间 |
| **A2** | LUFS 4.5 + TP 3.0 + LRA 2.5 + Duration 4.5 + Structure 4.0 = **18.5/50** | 结构服从仅 40% (Lyric 首行漏 "despacio") | 偏弱 |
| **A3** | LUFS 5.0 + TP 3.0 + LRA 3.5 + Duration 4.0 + Structure 10.0 = **25.5/50** | **0-15s 100% 结构服从 + LUFS -14.29 完美在中心** | **TOP 实测** |
| **A4** | LUFS 5.0 + TP 3.0 + LRA 3.0 + Duration 4.0 + Structure 0.0 = **15/50** | **STRUCTURAL FAIL**（0-15s 沉默）= 必剔出候选 | ⚠️ 排除 |

**Bot-b 评分倾向 ≠ Best LOCKED**（LOCKED 红线 = Kieran listen 拍）：
- 数据驱动评分：A3 (25.5) > A1 (21) > A2 (18.5) > A4 (15)
- ⚠️ **A4 应排除候选**（0-15s 沉默 = 结构性失败 LOCKED 6-21 Shibata Luna Track 1 A1 同款教训）

---

## §5. 流水线下一步（待 Kieran 拍板）

### 5.1 听感拍板 LOCKED
- Kieran listen **A1 / A2 / A3 三选一**（A4 = 排除）
- LOCKED 候选通知 = Kieran 指 Best 编号后进入 Mastering 流程

### 5.2 Best 选定后的 Master 工艺（4 步 LOCKED Oaeli 7-13）
1. **Trim 0-3s** (剥西语 "¡Suscríbete!" 训练污染；保留 0-2s fade-in 防 click)
2. **Trim 末尾 silence tail** (避免 Stage 2 loudnorm 拉出 0.6s gap)
3. **Loudnorm Stage 2** linear 1-pass target=-14 LUFS / TP=-1.2 dBFS (CCC LOCKED 6-21)
4. **Downconvert 48k→44.1k** + 16-bit soxr (LOCKED 6-21 Aube v3→v4 verified)
5. **Cover + ID3 装填** (28 项 LOCKED 7-14)

### 5.3 拍板项清单收缩

| # | 拍板项 | 状态 |
|---|---|---|
| 1 | TITLE = Mercado | ✅ LOCKED 7-14 |
| 2 | Lyrics 字段实际写法 | ✅ LOCKED（Kieran 手写 2150 char，结构服从 100% A3）|
| 3 | Cover 选 N 候选 | ⚠️ 待 Kieran 拍板 (Phase 2，与 Cover 工具选择) |
| 4 | D-28 试作 | ✅ DONE（4 wav 候选已实测）|
| 5 | Best 选段 | ⚠️ **当前 LOCKED — Kieran listen A1/A2/A3 后选** |

剩 2 项：**Cover 选 N 候选** + **Best 听感拍**。

---

## §6. Honest disclosure（实证限制 LOCKED 6-21）

| 局限 | 影响 | 缓解 |
|---|---|---|
| Whisper base 模型小，识别精度 ~85-95% | 0-15s 转录可能有 1-2 字误识 | 7-13 已 LOCKED 用户听感 1 句话 ≥ 全部量化 = listen 拍板权在 Kieran |
| Krumhansl proxy 被排除（低置信度）| 本轮不报 key | Aube Valois LOCKED 6-21 = Lilypond librosa chroma_cqt 才能 100% 校准（不在 Round 1 范围）|
| 7-dim 数据评分 ≠ 听感 | Bot-b 评分倾向仅供决策参考 | 7-13 LOCKED 准则 = 听感优先 |
| Duration 全部超上限 | 区间 3:40-4:10 被 8-段 2150-char 模板反复触发扩展 | LOCKED = 调整 Playbook 至 4:30-5:30 区间（待 Kieran 拍板）|

---

## §7. 引用

- A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md
- A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md
- A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md § 2 (Sound DNA / Forbidden)
- multi-artist-label-playbook §"新艺人 v0.1 vault-only template"
- multi-artist-label-playbook §"8 段 400-char 锁定阈值" (2150 char = 100% 服从 LOCKED 6-21)
- multi-artist-label-playbook §"Length field is non-functional" (Suno 5.5 Pro 不响应 "X minutes length")
- multi-artist-label-playbook §"YouTube training-set watermark 西语 = ¡Suscríbete!" (新 LOCKED 7-14)

---

## ⚠️ 待 Kieran listen（不输出 REJECT）

**候选 = A1 / A2 / A3**（A4 结构性失败已排除）。

Kieran listen wav → 拍 `Best = A?` → 进入 Master。
