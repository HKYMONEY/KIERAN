---
title: Veloria Senda 风格内容规划 v0.2
version: v0.2
status: wip
updated: 2026-07-14
artist_code: A8
catalog_prefix: HR-A8-T{NN}
extends:
  - 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2（A8 数据卡）
  - 八位藝人流量權重曲風映射報告.md § Veloria Senda 行
covers: Latin Folk / World
market: 拉美 + 全球
priority: 🥈 P1
notes_vs_veloria: A5 Veloria = 黄昏 / A8 Veloria Senda = Latin Folk / World 双标定位不同
tags: [Veloria Senda, Latin Folk, World Music, v0.1, wip]
---

# Veloria Senda 风格内容规划 v0.1（wip）

> ⚠️ **本文档仅整理 vault 已锁事实，不擅自填充虚构。** Sound DNA / Suno Prompt / BPM 区间均需 Kieran 拍板。
> A5 Veloria（黄昏，Ambient Pop）≠ A8 Veloria Senda（Latin Folk / World）。两个艺人独立 project，不要混淆。

---

## 1. 已知事实（来自 HAEVO-8-ARTISTS LOCKED，2026-07-11 v1.0）

| 字段 | 值 | 来源 |
|---|---|---|
| ARTIST tag | `Veloria Senda` | 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md:323 |
| 主要语言 | es (主) + en (副) | 同上:325 |
| 主 Genre（RouteNote Primary）| **Latin** | 同上:326 |
| 副 Genre（RouteNote Secondary）| **World** | 同上:327 |
| Subgenre | **Latin Folk;World Music** | 同上:328 |
| Top 50 流量权重 | **#44-47 (Latin 类)** | 八位藝人:20, 30-Resources:329 |
| 目标市场 | 拉美 + 全球 | 30-Resources...:330 |
| 发行优先级 | 🥈 **P1（Top 44 推荐池）** | 八位藝人:120, 30-Resources:337 |
| Brand Bible | **TBD（建议创建）** | 30-Resources...:336 |
| Catalog Prefix | `HR-A8-T{NN}` | 30-Resources...:335 |
| 已发 Track | 0（尚未 Track 1）| grep -r "Veloria Senda"\|"HR-A8" /root/obsidian-sync 0 hit |

**结论**：A8 Veloria Senda 当前是 **v0.0 raw material 阶段**，相比 Oaeli 优先级更高（P1 vs P2），但同样缺所有 Sound DNA 内容。

---

## 2. 风格定位三层（v0.1 WIP，LOCKED 前全部待 Kieran 拍板）

### 2.1 Sound 层（区间，不写单值 LOCKED）

- ⚠️ **BPM 区间**：待 Kieran 拍板（Latin Folk 多 90-120 BPM，与 World Music 节奏型差异大）
- ⚠️ **Key 范围**：Dorian / Mixolydian / Pentatonic 待 Kieran 拍板（Latin Folk 异国调性明显）
- ⚠️ **传统乐器权重**：20-40% Acoustic Guitar / Charango / Quena / Cajón / Accordion 待 Kieran 拍板
- ⚠️ **人声比**：60-75% Female Vocal（Veloria Senda 默认女声）待 Kieran 拍板
- ⚠️ **Suno Vocal**：Female es-MX 或 es-PE（Andean 系音色）待 Kieran 拍板

### 2.2 Forbidden 层（v0.1 待 Kieran 拍板）

- ⚠️ 是否禁 Trap Influence（保持 Latin Folk 纯净度）
- ⚠️ 是否禁 EDM / Electronic（World Music 边界）
- ⚠️ 是否禁 纯西语 Old-school Tropical（与 Latin Folk 区隔）
- ⚠️ 是否禁 Reaggaeton 节拍（与 Oaeli 区别）
- ⚠️ 是否禁 多语种混声（Veloria Senda 走纯 es / es+en 双语 vs 后期拓展）

### 2.3 Business 层（KNOWN）

- **目标市场**：拉美（Mexico / Argentina / Peru / Bolivia / Chile / Colombia）+ 全球
- **流量入口**：#44-47 Latin Folk 推荐池（Sub-genre 较弱，主流 Latin 辅）
- **竞品 / Reference 候选**：⚠️ 待 Kieran 拍板（候选：Julieta Venegas / Mon Laferte（早 Andean 风）/ Susana Baca / Lhasa de Sela）

---

## 3. 外部研究输入（2026-07-14 借鉴参考）

> 来源：用户引入的对 Latin 西语市场 + Suno 5.5 适应度的外部研究报告。
> 处理：拆为「**结构性 / 可直接吸收**」与「**待 Kieran 拍板**」两类。

### 3.0 协作分位（直接吸收为 Strategic Direction）

- **Oaeli（A6）= Suno 主力"西语都市情绪"走量项目**。维持拉丁主盘审美，与 🥉 P2 RouteNote 优先级解耦。
- **Veloria Senda（A8）= 拉美人文 / World 编辑名片**。保留 🥈 P1，但编辑权重大于走量。
- 两者形成 **「Oaeli 量产 + Veloria 精制」** 双艺人组合。
- 长期愿景：**双艺人同一主题跨域对切**（同一"黎明"，Oaeli 都市早晨 vs Veloria Senda 高地黎明，共享封面系列）。

### 3.0.1 市场体量定位（结构性事实）

- 美区 Latin 音乐 2025 H1 批发收入 ~4.9 亿美元（+5.9% YoY，12 年连续增长，98% 流媒体，付费订阅 +10%）。
- 2024 拉美语音乐在美录音市场占比 8.1%，2025 保持 8%+。
- Latin Pop 近一年略有下滑（-1.29%），Latin Tropical 增速放缓 → Latin 主盘竞争激烈，需要差异化。
- 结论：Oaeli 站在「**高体量 + 高竞争**」池；Veloria Senda 在「**细分 + editorial 友好**」池。

### 3.0.2 Suno 5.5 适应度（结构性事实）

- Suno 对西语 Pop / Reggaeton / Latin Pop / Bachata / Corridos / Flamenco 已有成熟模板，Prompt 生态成熟。
- 对 Folk / World / 传统乐器（Charango / Quena / Cajón）支持偏"模拟感"，**容易听出 AI 边界**。
- **工艺结论**：器乐收敛 = 20-30% 泛化描述（acoustic guitar, light Latin percussion, flutes）；不要在 Prompt 强行点名细分乐器；改用 **场景 + 情绪 + 风格泛化词**（warm Latin folk ballad, organic acoustic, intimate female vocal）驱动。
- 节奏：Oaeli 80-95 BPM = Suno 默认最擅长；Veloria Senda 90-120 BPM 更偏氛围歌而非强 hook hit。

### 3.1 Lyrics Lab 主题候选（待 Kieran 拍板）

**Latin Folk / World 生活场景**：

| Category | 候选主题 |
|---|---|
| Time | Antes del amanecer（黎明前）/ Mediodía en la sierra（高地正午）|
| Weather | Lluvia en los Andes（高地雨季）/ Viento de la puna / Sequía |
| Relationship | Carta de lejos（远方来信）/ Madre ausente / Abuela |
| State | Cansancio de la tierra（耕作疲惫）/ Alegría compartida（共同庆祝）|
| Space | Mercado（早市）/ Cocina de campo / Camino de tierra |

### 3.2 Mood Library（待 Kieran 拍板）

- ⚠️ Andean 高地静谧
- ⚠️ Coastal 海岸小镇傍晚
- ⚠️ Mercado 早市晨光
- ⚠️ Camino 长途徒步

### 3.3 Reference Music Library（LOCKED 前不擅自写入）

⚠️ Kieran 待 Kieran 拍板：
- **Andean / Peruvian**：Susana Baca / Magaly Solier / Eva Ayllón
- **Mexican Folk**：Lila Downs / Natalia Lafourcade（早期 Casa）/ Mon Laferte（早期）
- **Boundary**：是否纳入 Lhasa de Sela（已逝，遗产艺术家）；是否纳入 Javiera Mena（CL electronic folk）

### 3.4 Visual DNA（待 Kieran 拍板）

- ⚠️ 摄影 vs illustration（Latin Folk 偏摄影 + 民俗元素）
- ⚠️ 色彩：Earthy（terracotta / adobe / sun-baked gold）+ 高地蓝
- ⚠️ 主体：女性背影（安第斯）/ 民俗物件（Charango / Poncho / 织物）/ 山景
- ⚠️ Logo & tag line：⚠️ 待 Kieran 拍板

### 3.5 Track 1 候选主题（LOCKED 前均待 Kieran 拍板）

⚠️ 候选场景矩阵（外部建议 = **"样板房"模式**：先 2-3 条，锁定品牌织物感）：

**首推两条主题（外部建议优先级）**：

1. **Andean 高地清晨**：与 Oaeli 都市黎明形成跨厂牌横切；模板可参考 Lina（市场晨光）+ 微霓 Track 2 「窓辺」（室内→户外）
2. **Mercado 早市**：拉美人文锚定；模板可与 Aube "Premier Matin"（巴黎清晨公寓）形成"Sun rise across culture"系列

**备选两条**：

- ⚠️ Coastal 海岸小镇傍晚：与 A5 Veloria 黄昏同时间但场景不同（拉美海岸 vs 拉美都市黄昏）
- ⚠️ Camino / 路上：与微霓 Track 2 「窓辺」(室内→户外) 形成 "户外节奏" 系列

**双版本策略（外部建议）**：

每条 Suno Track 都做 **主版本 + 备选版本**：
- 主版本：以 Latin Folk 为主，较多原声元素。
- 备选版本：略靠近 Latin Pop Ballad（鼓弱化、旋律更 pop），看实际流媒体表现再决定是否在后续规划中增加"Folk-Pop crossover"线。

**操作角色定位（外部建议 = 直接吸收）**：

- Veloria Senda KPI = **Playlist 命中率（World / Acoustic / Latin Folk lists）+ 长期完播率**，不是短期播放量峰值。
- 视觉 = **纪录感视觉**（市场、山景、手工织物）+ **轻字幕** + 文化切片。
- YouTube / Shorts 用纪录片镜头叙事。

---

## 4. 路线图（v0.1 WIP → LOCKED 待 Kieran 拍板）

| 阶段 | 内容 | 状态 |
|---|---|---|
| v0.1（本文件）| 现有事实 + 拍板区清单 | wip |
| v0.2 | Brand Bible § 1-4 | 待 Kieran 拍板 |
| v0.3 | Track 1 SOP 候选 4-8 段 | 待 Kieran 拍板 |
| v1.0 | Brand Bible LOCKED（参考 Weini v0.3 SPLIT 模式）| 待 Kieran 拍板 |
| v1.1 | Track 1 master + RouteNote 提交 | 待 Track 1 拍板 |

---

## 5. 拍板项清单（Kieran 决策区）

按优先级：

1. ⚠️ **Sound 层 5 项**：BPM 区间 / Key 范围 / 传统乐器权重 / 人声比 / Suno Vocal 语种
2. ⚠️ **Forbidden 层 5 项**：Trap / EDM / Tropical 浓 / Reaggaeton / 多语种
3. ⚠️ **Reference Music**：3-5 位 reference 艺人锁定
4. ⚠️ **Visual DNA**：摄影 vs illustration / 主色 / 主体 / tag line
5. ⚠️ **Track 1 主题**：4 候选（Andean / Coastal / Mercado / Camino）

每项需 Kieran 拍板才能进入 Brand Bible。我等待 ⚠️ 区被填。

---

## 6. 与 A5 Veloria 的区分（重要）

| 维度 | A5 Veloria | A8 Veloria Senda |
|---|---|---|
| 主方向 | 黄昏 / Ambient Pop | Latin Folk / World |
| 主 Genre | Pop | Latin (Subgenre: World) |
| Subgenre | Dream Pop;Indie Pop | Latin Folk;World Music |
| 流量池 | #29-35 Pop | #44-47 Latin |
| 优先级 | 🥉 P2 | 🥈 P1 |
| 语言 | en | es |
| 时段锚 | 黄昏 | 拉美全天 |

**禁止**把两个艺人合并 / 共用 Brand / 共用 Sound DNA。RouteNote Profile / Spotify Artist ID / Brand Bible 必须独立。

---

## 7. 严禁项

- ❌ 不擅自写 v0.2 Brand Bible 内容（必须 Kieran 拍板）
- ❌ 不擅自生成 Sound DNA 单值（区间模式 LOCKED 7-13）
- ❌ 不擅自锁定 Lyric SOP 字段
- ❌ 不擅自定 Forbidden 层（边界敏感）
- ❌ 不擅自跑 Suno 试作（必须先 Sound DNA 区间 LOCKED）
- ❌ 不与 A5 Veloria 共享任何字段（独立 artist，独立 project）

---

## 8. 引用

- 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2 (A8 数据卡)
- 八位藝人流量權重曲風映射報告.md（Veloria Senda 行 + 🥈 P1 优先级）
- 30-Resources/Music-Genres/RN-Genres-39.md（RouteNote 39 主 Genre 列表，已 LOCKED）
- hky:artist-operating-system（Brand Bible vs Track Playbook SPLIT LOCKED）
- hky:multi-artist-label-playbook（parallel artist 共用 D2-T/D2-D 后端）
