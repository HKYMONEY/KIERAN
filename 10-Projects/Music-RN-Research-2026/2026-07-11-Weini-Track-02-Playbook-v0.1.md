---
status: research
topic: track-playbook
artist: weini
track_id: T02
version: 0.1
target_release: 2026-09-11
created: 2026-07-11
updated: 2026-07-11
tags: [weini, track-02, suno-sop, routenote, release-planning]
related:
  - [[2026-07-11-Weini-Brand-Bible-v0.3]]
  - [[2026-07-11-Hermes-v2-Weini-COS-Plan-v0.1]]
---

# 微霓 Track 02 Playbook v0.1

**定位**: 单 Track 一次性 SOP. 9/11 发行窗口用完即归档.
**关系**: 与 [[2026-07-11-Weini-Brand-Bible-v0.3]] 互补 — Playbook = 单次执行, Bible = 永久规则.

---

## 0. Playbook 元数据

| 字段 | 值 |
|---|---|
| Track ID | T02 |
| 标题 | (待 Domain 1 锁定) |
| 计划发行 | **2026-09-11** |
| 目标流派 | Chinese Dream Pop / Ambient Pop |
| BPM | 74 (Recommended 启动值, 浮动 ≤ 4) |
| Key | (Track 1=Dm, Track 2 ≠ Dm → 推荐 F#m 或 Am) |
| Master LUFS | -14 / TP -1.2 / 44.1 kHz |
| Lyric 长度 | ≥ 400 char / 8 段 |
| Brand Bible 引用 | [[2026-07-11-Weini-Brand-Bible-v0.3]] § 1-13 |

---

## 1. 7 域 SOP 倒推时间表

| D-Day | 日期 | 动作 | Domain | 输出文件 |
|---|---|---|---|---|
| T-56 | 2026-07-17 | 主题/歌词 v0.2 LOCKED | Domain 1 | `t02-domain-1-theme-lyrics-v0.2.md` |
| T-49 | 2026-07-24 | Suno Prompt v1.0 LOCKED | Domain 2 | `t02-domain-2-suno-prompt-v1.0.md` |
| T-42 | 2026-07-31 | Suno 跑 4-8 段 + A/B/C/D 7 维度评分 | Domain 3 | `t02-domain-3-evaluation.md` |
| T-35 | 2026-08-07 | 母带 v1.0 LOCKED | Domain 4 | `t02-domain-4-master-v1.0.flac` |
| T-28 | 2026-08-14 | 封面 v1.0 + Canvas LOCKED (3000x3000) | Domain 5 | `t02-domain-5-cover.png` + `t02-canvas.mp4` |
| T-21 | 2026-08-21 | 元数据 + RouteNote 提交 | Domain 6 | `t02-domain-6-metadata.json` |
| T-14 | 2026-08-28 | D30 KPI + Editorial Pitch | Domain 7 | `t02-domain-7-pitch-deck.pdf` |
| T-7 | 2026-09-04 | Track 1 长安月发布 (同步拉流量) | 同步 | (Track 1 计划) |
| **T-0** | **2026-09-11** | **微霓 Track 02 发布** | — | (RouteNote 上线) |

**关键节点**: 今天 2026-07-11 = T-56, 锁定 Domain 1 主题/歌词方向.

---

## 2. Domain 1: 主题 / 歌词 (T-56 LOCKED)

### 状态: v0.1 草稿, 待 Kieran 审

**3 候选方向** (基于 Track 1 = 长安月 = 古都月 / 夜档):

| 候选 | 主题 | 意象池 | 与 Track 1 互补维度 |
|---|---|---|---|
| **A 窗与灯** | 现代都市 / 公寓窗台 / 室内独处 | 窗 / 灯 / 雨 / 玻璃 / 影子 / 茶 | 夜→室内 / 古都→现代 / 远→近 |
| **B 河岸夜行** | 城市河岸 / 慢步 / 路灯 | 河 / 灯 / 风 / 步 / 时间 | 夜→夜 / 古都→现代 / 远→近 |
| **C 通勤末班** | 地铁末班 / 城市归人 | 地铁 / 窗 / 灯 / 耳机 / 疲惫 | 夜→夜 / 古都→现代 / 月→灯 |

**推荐 A** (与 Track 1 "古都月" 最互补: 古都→现代 / 月→灯 / 远→近 / 夜→室内).

### Lyric 8 段结构模板 (A 候选)

```yaml
character_count_target: 480-550  # ≥ 400 触发 Suno 结构服从
押韵: AABB 严押韵
显式标签: [Intro] [Verse 1] [Pre-Chorus] [Chorus] [Verse 2] [Pre-Chorus] [Chorus] [Bridge: whisper] [Instrumental Break: piano solo] [Chorus] [Outro: long fade out]
意象映射: 5 元素 (窗/灯/雨/玻璃/影子) vs 5 母题 (等待/独处/时间/陪伴/留白)
```

**待 Kieran 拍板**: 选 A / B / C, 然后 bot-b 写完整 8 段歌词 v0.2.

---

## 3. Domain 2: Suno Prompt (T-49 LOCKED)

### 状态: 待 Domain 1 锁定后写

**基础模板** (来自 [[2026-07-11-Weini-Brand-Bible-v0.3]] § 3):

```
Suno Style of Music:
Chinese dream pop, ambient, intimate whisper vocal, soft piano,
ambient synth pad, cinematic, wide stereo, long reverb

7 项参数 (T02 Recommended 启动值):
- BPM: 74
- Key: F#m (Track 1 = Dm, T02 ≠ Dm)
- Length: 4:00
- Vocal: Female, whisper subtype
- Genre: Dream Pop
- Instrumental: False
- Style: Chinese dream pop
- Style Influence: 85%
- Weirdness: 20%
```

**Negative Prompt**: 直接引用 Bible § 3 8 行 (Permanent).

**Track 2 专项增量**:
- Lyric: Domain 1 v0.2 LOCKED 后的 8 段结构歌词 (≥ 400 char)

---

## 4. Domain 3: 评估 (T-42 LOCKED)

### 7 维度评分 (引用 haevo-a-r-control-table § 1.6)

| 维度 | 权重 | T02 目标 |
|---|---|---|
| DNA 符合度 | 25% | 5 秒内识别 "这是微霓" |
| 时长 | 15% | 3:50-4:10 (避免 Suno 直出硬上限 ~4:30, 母带留余量) |
| vocal 清晰度 | 15% | whisper 80%+ 听清 |
| field recording | 15% | 双层叠加 + organic (无 loop) |
| 5 段结构 | 10% | 8 段完整 (经 Lyric ≥ 400 char) |
| no drums | 10% | 完全无 pop drums / EDM / trap |
| key | 5% | pitch detection = F#m |
| 整体 (艺人) 哲学 | 5% | 触发"空间感"而非"歌曲感" |

**接受标准**: ≥ 85 = Best, 75-85 = Second, < 75 = Reject.

### 评估工具 (Permanent 引用 Bible)

- Whisper tiny.en / small (zh) 多窗口 transcript (0-5s / 0-15s / 0-30s / 全文)
- ffmpeg loudnorm 2-pass LUFS / TP 检测
- librosa chroma_cqt Key 检测
- 听感 7 维度评分 (Kieran + bot-b)

### 3 轮回退策略 (引用 haevo-a-r-control-table § 1.7)

```
Round 1 失败 → 改 prompt 关键 1-2 词 → Round 2 (4 段)
Round 2 失败 → 改 Suno 参数 (Weirdness 25→40, Style Influence 75-85 微调) → Round 3 (4 段)
Round 3 失败 → 接受 Second best (75-85), Domain 4 修补, 标注 "需手工修补"
```

---

## 5. Domain 4: 母带 (T-35 LOCKED)

### 引用 Bible § 6 (Permanent)

| 参数 | 锁定值 |
|---|---|
| LUFS | -14 |
| True Peak | -1.2 dBTP |
| Sample Rate | 44.1 kHz |
| LRA | ≥ 6 LU |

### 母带命令 (T02 专项)

```bash
# 2-pass loudnorm (EBU R128 K-weighting + dual-gate)
ffmpeg -y -i t02-raw-best.flac \
  -af "loudnorm=I=-14:TP=-1.2:LRA=11:measured_I=-16:measured_TP=-1.5:measured_LRA=8:measured_thresh=-26:offset=0.5:linear=true:print_format=summary" \
  -ar 44100 -ac 2 -c:a flac \
  t02-mastered-v1.0.flac

# 4s 末尾 fade-out (避免 Suno 直出硬切)
ffmpeg -y -i t02-mastered-v1.0.flac \
  -af "afade=t=out:st=0:d=4" \
  t02-mastered-v1.0-final.flac
```

### ID3 Tags (13 字段, T02 专项值)

待 Domain 6 元数据完成后填.

---

## 6. Domain 5: 视觉 (T-28 LOCKED)

### 三位一体 (引用 Bible § 2.4)

| 资产 | 规格 | T02 主题候选 |
|---|---|---|
| Cover 3000x3000 | 杜絕行銷文字 | (A) 窗 / 雨 / 灯 / 室内静物 |
| Motion Art | 起始帧 = Cover | (Apple Music) |
| Canvas 15s | 竖屏 Loop | (Spotify) |

### 视觉元素 (引用 Bible Permanent)

- 核心元素: 窗 / 灯 / 雨 / 玻璃 / 影子 (候选 A 主题)
- Camera: 长焦 / 浅景深 / 胶片颗粒 / 雾化光 / 电影感
- 色彩: 月白 / 雾蓝 / 墨灰 / 深青 / 暖金 (点缀)
- ❌ 禁止: 高饱和霓虹 / 卡通萌系 / K-pop / 二次元

### Cover 提示词 (Ideogram / Midjourney, T02 候选 A)

```
Long-focus photograph of an apartment window at night, soft raindrops on glass,
single warm lamp on the table, intimate interior, cinematic composition,
fog-filtered city light outside, muted blue-grey palette with warm gold accent,
no people, no text, no logo, contemplative atmosphere, 35mm film grain
```

---

## 7. Domain 6: 元数据 (T-21 LOCKED)

### RouteNote 39-list 提交 (引用 Bible § 5)

| 字段 | T02 值 |
|---|---|
| Title | (Domain 1 LOCKED 后填) |
| Main Genre | **Pop** |
| Secondary Genre | **World** |
| Subgenre (ID3) | **Mandopop;華語流行;Taiwanese Pop** (v0.4 修订, 官方映射) |
| Language | zh-Hans |
| Release Date | 2026-09-11 |
| UPC | (申请) |
| ISRC | (申请) |
| Label | Haevo Records |
| Composer/Lyricist/Producer | XIAOYANG ZHANG |
| AI Disclosure | "AI-generated music under Haevo Project" |

### 验证 SOP (Permanent)

提交前必须跑 `validate_genre.py "Weini"` fail-closed 验证.

---

## 8. Domain 7: Editorial Pitch + D30 KPI (T-14 LOCKED)

### Editorial Pitch 平台 (引用 Bible § 8)

| 平台 | Pitch 提前期 | T02 Pitch 提交日 |
|---|---|---|
| Spotify | T-14 | 2026-08-28 |
| Apple Music | T-21 | 2026-08-21 |
| Deezer | T-14 | 2026-08-28 |
| Qobuz | T-14 | 2026-08-28 |
| **网易云** | T-7 | 2026-09-04 |
| **抖音** | T-3 | 2026-09-08 |

### D30 KPI 目标 (T02 候选)

| 指标 | 目标 | Source |
|---|---|---|
| Save Rate | ≥ 3% (Brand Establishment baseline) | H001 假设验证 |
| Completion Rate | ≥ 60% | 行业标准 |
| Skip Rate | < 35% | 行业标准 |
| Editorial Playlist Add | ≥ 1 (Deezer Sleep 或 Spotify Deep Focus) | 数据 |
| Comments | ≥ 30 条 (D+30) | [[08-audience-memory]] 录入 |

### D90 KPI (Performance Review 触发)

见 [[2026-07-11-Weini-Brand-Bible-v0.3]] § 10.

---

## 9. Track 1 同步 (T-7)

**Track 1 长安月** 计划 T-7 (2026-09-04) 发布. T02 发布时 Track 1 已上线 7 天 = 拉流量入口.

**协同动作**:
- T02 Smart Link 含 Track 1 "Listen Also" 链接
- Track 1 Canvas / Cover 复用 T02 视觉元素 (品牌一致性)
- 网易云 / 抖音两个 Track 同步推广

---

## 10. Post-Release: Performance Review (D+7 / D+30 / D+90)

**触发**: Kieran 手动跑命令, Hermes Telegram 提醒.

| 节点 | 提醒日 | 数据源 | 输出 |
|---|---|---|---|
| D+5 提醒 | 2026-09-16 | (Kieran 决定跑) | `track-performance-review.py --offset D7` |
| D+28 提醒 | 2026-10-09 | (Kieran 决定跑) | `... --offset D30` |
| D+88 提醒 | 2026-12-08 | (Kieran 决定跑) | `... --offset D90` + DNA 更新 |

**详见 [[2026-07-11-Weini-Brand-Bible-v0.3]] § 10 Performance Review SOP**.

---

## 11. 待解决问题

- [ ] **Domain 1 LOCKED**: 主题/歌词方向 (候选 A/B/C, 推荐 A 窗与灯)
- [ ] **Track 2 标题**: 待 Domain 1 锁定
- [ ] **Track 1 长安月 LOCKED 状态**: 影响 T-7 同步策略
- [ ] **Validate Genre 脚本验证**: 提交前必跑
- [ ] **Performance Review 脚本**: `track-performance-review.py` 待创建
- [ ] **Track 2 9/11 vs Track 1 9/4 时间差**: 7 天是否最优, 验证 H005/H006

---

## 12. 引用

- [[2026-07-11-Weini-Brand-Bible-v0.3]] (永久规则源)
- [[2026-07-11-Hermes-v2-Weini-COS-Plan-v0.1]] (Hermes 调度框架)
- haevo-a-r-control-table SKILL.md (Domain 3 7 维度 + 3 轮回退)
- multi-artist-label-playbook SKILL.md v4.7 (RouteNote 39-list + v4.2 Genre)
- haevo-aube-qc-framework (TP -1.2 / 44.1kHz / 母带 SOP)
- suno-5.5-ambient-workflow SKILL.md v4.7 (Whisper multi-window 评估)
- [[2026-07-11-Weini-Suno-CN-Test-v0.1]] (跳过, 不跑 5 项中文测试)

---

⚠️ **[v0.1 草稿, 待 Kieran 审]**

📋 **决策问题**:

1. 🔥 **Domain 1 主题方向 A / B / C 选哪个?** (推荐 A 窗与灯)
2. **T02 Key 选 F#m / Am / 其他?** (Track 1 = Dm 锁, T02 ≠ Dm)
3. **7 域 SOP 倒推时间表 (T-56 ~ T-0) 是否同意?**
4. **T-7 Track 1 同步发布策略是否同意?** (9/4 长安月 + 9/11 T02)
5. **D+5 / D+28 / D+88 Hermes 提醒机制是否同意?**