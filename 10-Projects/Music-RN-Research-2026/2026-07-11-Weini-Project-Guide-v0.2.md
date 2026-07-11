---
status: research
topic: artist-brand-dna
artist: weini
version: 0.2
based_on: 微霓藝人項目規劃書 (Kieran 原稿)
created: 2026-07-11
updated: 2026-07-11
tags: [music-distribution, weini, brand-dna, ambient, chinese, haevo-records]
---

# 微霓 (Weini) 项目指南 v0.2

**厂牌**: Haevo Records
**Track 2 计划发行**: 2026-09-11
**本指南定位**: 微霓 Track 2 规划期使用的品牌/技术规范文档, Track 1 LOCKED 后升级为 v1.0 终版

---

## 修订日志 (changelog)

| 版本 | 日期 | 修订内容 | 来源 |
|---|---|---|---|
| v0.1 | 2026-07-10 | Kieran 原稿 | 微霓藝人項目規劃書 |
| v0.2 | 2026-07-11 | (1) BPM 改双层 (72-84 生涯 / 72-78 前 5 首) | Kieran 2026-07-11 |
| v0.2 | 2026-07-11 | (2) BPM 浮动 ≤ 4 (Stage 1) | Kieran 2026-07-11 |
| v0.2 | 2026-07-11 | (3) Vocal 比例显式写 100F + Suno 可执行词 | Suno v5.5 + playbook v4.7 |
| v0.2 | 2026-07-11 | (4) Suno 7 项参数 + 8 行 Negative Prompt | haevo-a-r-control-table skill |
| v0.2 | 2026-07-11 | (5) RouteNote 39-list 硬约束 + v4.2 Genre 矩阵 | multi-artist-label-playbook v4.7 |
| v0.2 | 2026-07-11 | (6) Mastering TP -1.2 / LRA / 44.1kHz | haevo-aube-qc-framework |
| v0.2 | 2026-07-11 | (7) Lyric ≥ 400 char / 8 段结构 | suno-lyrics-400-char-threshold |
| v0.2 | 2026-07-11 | (8) 跳过 5 项 Suno 中文能力测试 (已确认 Suno 付费不换) | Kieran 2026-07-11 |

---

## 一、艺人核心定位与品牌身份

| 维度 | 锁定值 |
|---|---|
| **核心身份** | 华语另类流行艺术家 / 华语氛围流行旗舰艺人 |
| **艺术定位** | 东方美学灵魂 + 现代 Alternative Pop / Dream Pop / Ambient 声景 |
| **市场角色** | Haevo Records 进入全球华语市场的全流量入口 (台港澳东南亚 + 海外华人) |
| **品牌定位** | "现代东方氛围感 IP" (vs 传统古风) |
| **Brand Mission** | 以现代音乐语言重新诠释东方情绪, 让全球听众通过当代流行音乐感受东方美学的宁静、留白与诗意 |

---

## 二、艺人 DNA 矩阵

### 2.1 Artist DNA (5 维)

| 类型 | 内容 |
|---|---|
| **Core Genre** | Chinese Alternative Pop |
| **Primary Sound** | Ambient Pop |
| **Secondary Sound** | Dream Pop |
| **Supporting Elements** | Guofeng / Cinematic / Indie Pop |
| **Vocal Ratio** | **100F** [v0.2 修订: 显式写入, 此前仅说"有机人声"] |

### 2.2 Visual DNA

#### 核心元素 (8 选 N)
月 / 雾 / 风 / 烟 / 山 / 水 / 灯 / 雁

#### Camera Language
- 长焦 / 浅景深 / 胶片颗粒 / 雾化光 / 柔焦 / 电影感构图

#### 固定色彩
- 月白 / 雾蓝 / 墨灰 / 深青 / 暖金 (点缀)

#### 禁止元素
- ❌ 高饱和霓虹 / ❌ 卡通萌系 / ❌ K-pop 偶像妆造 / ❌ 二次元角色封面

### 2.3 Emotional DNA

| 关键词 | 写作特点 |
|---|---|
| 静 / 梦 / 思念 / 留白 / 夜 / 孤独 / 希望 | 留白 / 少叙事多意象 / 情绪克制 / 避免网络流行语 / 避免说教 |

### 2.4 Music DNA (v0.2 双层 Tempo DNA)

#### [v0.2 修订: Kieran 2026-07-11 双层方案]

**Artist Tempo DNA (全生涯)**:
- 范围: **72–84 BPM**
- 边界: 拒绝 ≥ 85 BPM (避免主流流行抒情)
- 边界: 拒绝 < 70 BPM (破坏 ambient breathing)

**Brand Establishment (Track 1–5)**:
- 范围: **72–78 BPM**
- 相邻浮动: **≤ 4 BPM**
- 例外: 概念专辑 / 风格转型 (需 Domain 6 + Domain 7 同步变更)

**Brand Expansion (Track 6–10)**:
- 范围: **76–82 BPM**
- 相邻浮动: **≤ 4 BPM**
- 目标: 平稳过渡到全生涯 Tempo DNA

**Mature Catalog (Track 11+)**:
- 范围: **72–84 BPM 全域**
- 触发条件: 10 首累计 Save rate ≥ 3% + D90 长尾健康

**例 (Track 1-5 Brand Establishment 浮动表)**:

| Track | BPM |
|---|---|
| 1 | 74 |
| 2 | 76 |
| 3 | 73 |
| 4 | 78 |
| 5 | 75 |

#### Harmony (v0.2 修订: Key 池扩展)

**Key 池 (5 minor, 5 选 1)**:
- D minor / A minor / C minor / E minor / F# minor
- **禁**: C major / A major
- **Track N 跟 Track N-1 不可同 key** (防姐妹曲 cannibalization)

#### 编制 / 混音

| 维度 | 锁定值 |
|---|---|
| **长混响 (Long Reverb)** | 必填 |
| **简约编配 (Sparse Arrangement)** | 段间停顿 ≥ 4s |
| **宽立体声 (Wide Stereo)** | +0.3 到 +0.7 相关性 (commercial 标准) |

---

## 三、音乐制作与技术规格

### 3.1 人声特质 (Vocal DNA)

| 维度 | 描述 | Suno 可执行词 [v0.2 新增] |
|---|---|---|
| Organic Vocal Presence | 有机人声存在感 | `organic human vocal` |
| Intimate | 亲密 | `whisper` |
| Breathy | 带气息感 | `soft breathy vocal` |
| 情感细腻 | Emotional | `emotional delivery` |

### 3.2 制作标准 (v0.2 修订: 加 TP / LRA / sample rate)

| 参数 | 锁定值 | 来源 |
|---|---|---|
| **Mastering LUFS** | **-14** (国际串流标准) | Kieran 原稿 |
| **True Peak** | **-1.2 dBTP** [v0.2 新增] | haevo-aube-qc-framework (TP -1.0 是边界值, 工程目标 -1.2 给 AAC 0.2 dB 余量) |
| **LRA** | **≥ 6 LU** [v0.2 新增] | 动态范围最低标准 |
| **Sample Rate** | **44.1 kHz** [v0.2 新增] | Red Book CD 标准, Qobuz/Apple/Tidal 路由 |
| **Vocal 比例** | **100F** (微霓全女性) | playbook v4.7 |
| **Language** | zh-Hans 主 + zh-Hant 副 (同步提交) | Kieran 原稿 |

### 3.3 AI 辅助开发 (Suno v5.5 Pro)

**用户锁定**: Suno 付费用户, **不更换平台**, 跳过 5 项中文能力测试 [v0.2]

#### 模板 A: Dream Pop (主推)

```
Suno Style of Music:
Chinese dream pop, ambient, intimate whisper vocal, soft piano,
ambient synth pad, cinematic, wide stereo, long reverb

7 项 Suno 参数:
- BPM: 74 (Track 1)
- Key: D minor
- Length: 4:00 (显式, 因 Style field "X minutes length" 无效)
- Vocal: Female, whisper subtype
- Genre: Dream Pop
- Instrumental: False
- Style: Chinese dream pop (完整描述, Style slider = None)
- Style Influence: 85%
- Weirdness: 20%
```

#### 模板 B: Alternative Ballad (备选)

```
Suno Style of Music:
Mandarin alternative pop, intimate whisper vocal, piano, organic strings,
wide stereo, emotional delivery, ambient ballad

7 项 Suno 参数:
- BPM: 76
- Key: A minor
- Length: 4:00
- Vocal: Female, whisper subtype
- Genre: Alternative Pop
- Instrumental: False
- Style: Mandarin alternative pop
- Style Influence: 85%
- Weirdness: 20%
```

#### Negative Prompt (8 行锁定, 5 类必填) [v0.2 新增]

基于 haevo-a-r-control-table pitfall 3: Negative ≥ 8 行 → Suno 命中率 89% (vs 31%)

```
❌ drums, drum kit, hi-hat, snare, trap beat, EDM beat, kick drum      [Drums]
❌ commercial chorus, radio structure, catchy hook, sing-along chorus [Structure]
❌ white noise, lo-fi loop, vinyl crackle, tape hiss                    [Loop]
❌ bright major chord, C major, A major, major key                     [Key]
❌ 古筝 solo, guzheng solo, 琵琶 solo, pipa solo, 笛子 solo,          [中文污染]
   二胡 solo, erhu solo
❌ 戏腔, 京剧, 京劇, 戏曲, 越剧, 黄梅戏, opera vocal, belting         [中文污染]
❌ 高音飙歌, 海豚音, whistle register, 维塔斯, Vitas-style           [中文污染]
❌ MCSC 喊麦, 电音喊麦, Chinese EDM shout, 网络流行语, meme phrase   [中文污染]
```

### 3.4 Lyric 硬约束 [v0.2 新增]

基于 suno-lyrics-400-char-threshold 实证: 168 char 5 段 → Suno 自由发挥 (0% 服从) vs ≥ 400 char 8 段 → 100% 服从

| 约束 | 锁定值 |
|---|---|
| **总字符数** | **≥ 400 char** |
| **结构** | **8 段 (Intro / V1 / Pre-Chorus / C / V2 / Pre-Chorus / C / Bridge / Instrumental Break / C / Outro fade out)** |
| **押韵** | AABB 严押韵 |
| **显式标签** | 必须含 `[Pre-Chorus]` + `[Bridge: ...]` + `[Instrumental Break: ...]` + `[Outro: long fade out, ...]` |

### 3.5 优选方向 / 规避区

**优选方向**: 华语梦幻流行 (Chinese Dream Pop) + 氛围抒情 (Mandarin Ambient Ballad)

**Encouraged**:
- ✔️ Piano / ✔️ Organic Strings / ✔️ Ambient Synth / ✔️ Cinematic Texture / ✔️ Natural Field Recording

**规避区 (避免塑料感)**:
- 戏腔 / 京剧 / 戏曲唱法 (改现代合成器)
- 古筝 / 琵琶 / 笛子 solo (改 ambient synth 隐约东方元素)

---

## 四、分发与算法路由策略

### 4.1 RouteNote 动态提交策略 (v4.2 标准) [v0.2 修订: 显式 39-list 硬约束]

**硬约束**: RouteNote 主+次曲风必须从 39 个官方选项中选 (2026-07-01 实测 dropdown 锁定). Mandopop / Chinese Indie / Ambient Pop / Guofeng **不在 dropdown** → 进 Subgenre (ID3 多值) 字段

| 提交类型 | 主曲风 (Main) | 次曲风 (Secondary) | Subgenre (ID3 多值) |
|---|---|---|---|
| 现代国风流行 | **Pop** | **Alternative** | Chinese Folk;Mandopop;Alternative R&B |
| 传统器乐融合 | **World** | **Pop** | Chinese Folk;Ambient;World |
| 功能性纯音乐 | **Electronic** | **Alternative** | Ambient;Atmospheric;Functional |

**微霓默认提交**: 主 Pop + 次 World (对齐 playbook v4.2 Weini 矩阵, 锁定 Mandopop Editorial 入口)

### 4.2 目标微曲风 (Subgenre 字段)

Mandopop / Chinese Indie / Ambient Pop / Guofeng

### 4.3 功能性入口

锁定全球「睡眠 / 专注 / 冥想」功能型歌单市场

**3 平台分仓策略** [v0.2 新增]:
| 平台 | 入口 | 优先级 |
|---|---|---|
| 国际 Editorial | Deezer Sleep/Focus + Qobuz Hi-Res | 中 |
| 国际算法 | Spotify Deep Focus (37i9dQZF1DWZeKfjuA5x0e) / Ambient Relaxation (37i9dQZF1DX3Ogo9pFvBkY) | 中 |
| **国内流量** | **网易云助眠 / 国风纯音 / 抖音 BGM 库** | **高** |

### 4.4 影视联动 (OST Strategy)

作品需具备「影视感 (Cinematic)」, 适合作为影视 / 短片 / 游戏 OST

**OST 投递优先级** [v0.2 新增]:
1. 网易云 OST 歌单
2. 抖音 BGM 库 (AI disclosure 第 1 行)
3. Spotify Cinematic Focus Editorial

**OST 7 资产必填**: Cover / Canvas / Motion Art / Lyrics / Credits / Metadata / ISRC / Pitch

---

## 五、品牌视觉资产标准化 (Visual Asset SOP)

### 三位一体视觉套件

| 资产 | 规格 | 平台 |
|---|---|---|
| **静态封面 (Cover)** | 3000×3000px, **杜絕行銷文字** | 全平台 |
| **动态封面 (Motion Art)** | 起始帧必须与封面一致 | Apple Music |
| **15s 竖屏 Loop (Canvas)** | Spotify Canvas 移动端增强收藏 | Spotify |

---

## 六、品牌边界 (Not-To-Do List)

### 流派禁区

| 禁区 | 理由 |
|---|---|
| ❌ EDM Festival / Dancehall | 破坏氛围感 |
| ❌ Trap Rap / Phonk | 与东方美学基调不符 |
| ❌ K-pop Idol / Hyperpop | 受众不匹配 |
| ❌ Metal / Anime Rock | 演算法路由混乱 |

### 元素禁区 (来自 Visual DNA + Negative Prompt)

- ❌ 高饱和霓虹 / ❌ 卡通萌系 / ❌ K-pop 偶像妆造 / ❌ 二次元角色封面
- ❌ 古筝 / 琵琶 / 笛子 solo (戏腔 / 京剧 / 戏曲)

---

## 七、流派比例分配 (Track 1-10 全生涯)

| 类型 | 比例 | 调整说明 |
|---|---|---|
| Chinese Alternative Pop | 40% | 厂牌旗舰调性 |
| Dream Pop | 25% | Deep Focus Editorial 入口 |
| Ambient Pop | 20% | Ambient Relaxation Editorial 入口 |
| Guofeng Fusion | 10% | 抖音 / 小红书 BGM 库入口 |
| Instrumental | 5% | 睡眠 / 专注功能型入口 |

**未来调整**: Track 6 后根据 Save rate / D90 长尾数据优化比例

---

## 八、Track 2 SOP 9/11 倒推时间表 [v0.2 新增]

**D-Day**: 2026-09-11 (Track 2 发行)

| D-Day | 日期 | 动作 | Domain |
|---|---|---|---|
| T-56 | 2026-07-17 | 主题/歌词 v0.2 LOCKED | Domain 1 |
| T-49 | 2026-07-24 | Suno Prompt v1.0 LOCKED | Domain 2 |
| T-42 | 2026-07-31 | Suno 跑 4-8 段 + A/B/C/D 7 维度评分 | Domain 3 |
| T-35 | 2026-08-07 | 母带 v1.0 LOCKED (-14 LUFS / -1.2 TP / 44.1kHz) | Domain 4 |
| T-28 | 2026-08-14 | 封面 v1.0 + Canvas LOCKED (3000×3000) | Domain 5 |
| T-21 | 2026-08-21 | 元数据 + RouteNote 提交 | Domain 6 |
| T-14 | 2026-08-28 | D30 KPI + Editorial Pitch | Domain 7 |
| T-7 | 2026-09-04 | Track 1 长安月发布 (同步拉流量) | 同步 |
| **T-0** | **2026-09-11** | **微霓 Track 2 发布** | — |

**关键节点**: 今天 2026-07-11 = T-56, 锁定 Domain 1 主题/歌词方向

---

## 九、待解决问题 (本版本未锁)

- [ ] Track 2 主题 / 歌词方向 (Domain 1) — v0.3 锁定
- [ ] Track 1 长安月 LOCKED 状态确认
- [ ] Suno 中文能力 5 项测试 (已确认跳过)
- [ ] Key 池扩展 F#m 是否纳入 Track 2 (Track 1 = Dm 锁)
- [ ] Stage 2 Brand Expansion BPM 范围 76-82 是否调整
- [ ] Mastering 母带 SOP (ffmpeg 2-pass loudnorm) 具体命令

---

## 十、引用 (References)

- 微霓藝人項目規劃書 (Kieran 原稿 v0.1)
- haevo-a-r-control-table SKILL.md (Domain 3 7 维度 + Failure Criteria + Negative ≥ 8 行)
- multi-artist-label-playbook SKILL.md v4.7 (RouteNote 39-list v4.2 + Weini Pop/World 矩阵)
- suno-5.5-ambient-workflow SKILL.md v4.7 (Whisper multi-window 评估方法)
- haevo-aube-qc-framework (TP -1.2 / 44.1kHz 母带标准)
- suno-lyrics-400-char-threshold 实证 (8 段结构 ≥ 400 char)
- 2025-2026 全球與台灣音樂曲風流量決策指南 (市场数据基础)

---

⚠️ **[v0.2 草稿, 待 Kieran 审]**

📋 **决策问题**:

1. 双层 Tempo DNA (72-84 生涯 / 72-78 前 5 首) 是否锁定
2. Key 池 5 minor (Dm/Am/Cm/Em/F#m) 是否同意
3. Suno 7 项参数 + 8 行 Negative Prompt 锁定值是否同意
4. Track 2 SOP 9/11 倒推时间表 T-56 (7-17) 锁定 Domain 1 是否同意
5. 流派比例 40/25/20/10/5 是否同意 (或调整)