---
title: Oaeli 风格内容规划 v0.2
version: v0.2
status: wip
updated: 2026-07-14
artist_code: A6
catalog_prefix: HR-A6-T{NN}
extends:
  - 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2（A6 数据卡）
  - 八位藝人流量權重曲風映射報告.md § Oaeli 行
covers: Spanish Ambient Pop / Latin
market: 西班牙 + 拉美 + 全球
priority: 🥉 P2
tags: [Oaeli, Spanish Ambient Pop, Latin, v0.1, wip]
data_sources_verified: yfinance (K-line) + RouteNote 39 Genre 列表
data_sources_unknown: Spotify Editorial Playlists (未授权 / 趋势不可直接拿)
vault_truth_only: true
---

# Oaeli 风格内容规划 v0.1（wip）

> ⚠️ **本文档仅整理 vault 已锁事实，不擅自填充虚构。** 任何 Sound DNA / Suno Prompt / BPM 区间都需要 Kieran 拍板后才能进入。
> 编程面：见 `hky:artist-operating-system` skill（Brand Bible vs Track Playbook 分层 LOCKED）。

---

## 1. 已知事实（来自 HAEVO-8-ARTISTS LOCKED，2026-07-11 v1.0）

| 字段 | 值 | 来源 |
|---|---|---|
| ARTIST tag | `Oaeli` | 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md:279 |
| 主要语言 | es (主) + en (副) | 同上:280 |
| 主 Genre（RouteNote Primary）| **Latin** | 同上:281 |
| 副 Genre（RouteNote Secondary）| **Alternative** | 同上:282 |
| Subgenre | **Latin Pop;Spanish Pop** | 同上:283 |
| Top 50 流量权重 | **#44 (Latin Pop)** | 八位藝人:18 |
| 目标市场 | 西班牙 + 拉美 + 全球 | 30-Resources...:285 |
| 发行优先级 | 🥉 **P2（长尾稳定）** | 30-Resources...:292 |
| Brand Bible | **TBD（建议创建）** | 30-Resources...:291 |
| Catalog Prefix | `HR-A6-T{NN}` | 30-Resources...:290 |
| 已发 Track | 0（尚未 Track 1）| grep -r "Oaeli"\|"HR-A6" /root/obsidian-sync 0 hit |

**结论**：A6 Oaeli 当前是 **v0.0 raw material 阶段**，只有标签订位 / 流量定位 / 优先级，没有任何 Sound DNA / Track Playbook / 已发 Track。

---

## 2. 风格定位三层（v0.1 WIP，LOCKED 前全部待 Kieran 拍板）

### 2.1 Sound 层（区间，不写单值 LOCKED）

- ⚠️ **BPM 区间**：80-95 BPM 待 Kieran 拍板（Latin Pop 常驻范围 vs Spanish Ambient Pop 慢曲需要）
- ⚠️ **Key 范围**：自然小调 / Dorian 待 Kieran 拍板（Spanish Pop 调性直觉偏 Phrygian / Andalusian）
- ⚠️ **结构**：Standard Latin Pop（A 段 + Coro + Verso + Puente）vs Slow Ambient 4-段均待验证
- ⚠️ **人声比**：70-80% Female（Oaeli 默认女声）待 Kieran 拍板
- ⚠️ **Suno Vocal**：Female es-MX 或 es-ES 待 Kieran 拍板

### 2.2 Forbidden 层（v0.1 待 Kieran 拍板）

- ⚠️ 是否禁 Reaggaeton 节拍（与传统 Latin Pop 区隔）
- ⚠️ 是否禁 Trap Influence（保持 Latin Pop 纯净度）
- ⚠️ 是否禁 探戈 / 弗拉门戈过浓（保持 Modern 感）
- ⚠️ 是否禁 西语 Old-school Vocal Timbre（保持 2025-2026 质感）

### 2.3 Business 层（KNOWN — 来自八位藝人流量權重曲風映射）

- **目标市场**：西班牙（ES）+ 拉美（Mexico / Argentina / Colombia / Chile）+ 全球
- **流量入口**：#44 Latin Pop 推荐池（RouteNote / Spotify Editorial）
- **竞品**：艺人方向待 Kieran 拍板（候选：Rigoberta Bandini / Natalia Lacunza / Rosalía 早期？）

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

**Modern Life Contexts（Spanish / Latin 生活场景）**：

| Category | 候选主题 |
|---|---|
| Time | La madrugada（凌晨）/ El alba（黎明）/ Atardecer（黄昏）|
| Weather | Lluvia（雨）/ Calor（暑）/ Viento（风）|
| Relationship | Primera cita（首次约会）/ Carta（信件）/ Última llamada（最后一通电话）|
| State | Soledad sin drama（无戏剧感的孤独）/ Alegría pequeña（小喜悦）|
| Space | Estación del metro / Mirador / Cocina de abuela |

### 3.2 Mood Library（待 Kieran 拍板）

- ⚠️ Mediterranean 静谧
- ⚠️ Iberian Siesta 慵懒
- ⚠️ Modern Madrid 都市独居
- ⚠️ Mexico City 23:00 一人散步

### 3.3 Reference Music Library（候选 reference 锁定前不擅自写入）

⚠️ Kieran 待 Kieran 拍板：
- Spanish Pop：Rigoberta Bandini / Natalia Lacunza / Cariño / Veintiuno
- Latin Pop：Mon Laferte / Carla Morrison（早）/ Francisca Valenzuela
- Boundary：是否纳入 Rosalía / Nathy Peluso（这些是 mega artist，避免直接对标导致 KPI 错位）

### 3.4 Visual DNA（待 Kieran 拍板）

- ⚠️ 摄影 vs illustration（Spanish Pop 偏 illustration 多）
- ⚠️ 色彩：Mediterranean warm（terracotta / dusty rose / sun-bleached gold）
- ⚠️ 主体：女性背影 / 家具静物 / 城市建筑远景
- ⚠️ Logo & tag line：⚠️ 待 Kieran 拍板

### 3.5 Track 1 候选主题（LOCKED 前均待 Kieran 拍板）

⚠️ 候选场景矩阵（外部建议升级 = **4 × N 结构**）：

| 场景原型 | 情绪变体 |
|---|---|
| 清晨 Madrid 公寓 | (a) 孤独醒来 / (b) 城市白噪音独处 |
| 夜晚 Mexico City 独行 | (a) 末班车 / (b) 街区灯下漫步 |
| 地中海海边白日 | (a) 沙滩午后 / (b) 海风晚餐 |
| 地铁站 / 城市眺望台 | (a) 高峰通勤 / (b) 凝视地平线 |

- **首批 6-8 条 Track 全压给 Oaeli**，作为 Suno 在西语 Pop 方向的整体模型行为验证。
- 跨艺人协同：与 Aube Valois（巴黎清晨）、Luna（夜晚 Tokyo）、Weini（夜晚台北）形成跨厂牌横切。
- Kieran 待拍板：4 × N 中具体选哪条 Track 1。

### 3.6 Lyrics / Text Vault 路线图（结构性输入 LOCKED）

> 来源：用户 2026-07-14 提出"建立独立 Lyrics / Text Vault"。
> 本节 = 借鉴参考 / 路线图标注，**不立即建文件**。

**叙事主轴（已固化）**：

- 现代化西语城市生活的编年诗 — 真人都市记忆 + AI 声响。

**商业目标（已固化）**：

- 西语世界品牌（饮料 / 生活方式 / 城市文化节）的合作歌与 Campaign 曲目。

**结构化方向**：

- 升级自 `weini-cos/01-lyrics-lab/` 模式，但**改名**为 `lyrics-vault/`，因为定位从"每日 1 句"变为"长期文稿库"。
- 数据 schema = 我们 9 月 12 拉美数据库 vs 每月拉美日记 vs 拼合 cummulative corpus。

**Kieran 待拍板项（不擅自写 v0.2）**：

1. ⚠️ 数据 schema 字段定档（频率？单句 / 段落 / 多文稿？）
2. ⚠️ 是否纳入真实 / 改编日记内容（IP 风险评估）
3. ⚠️ 编辑流程（diary → 改编 → lyric 的去隐私/去重润色路径）
4. ⚠️ 与 Suno Prompt 的交付接口（是否提前 3个月预留 lyries buffer）
5. ⚠️ 品牌合作路径中"品牌限定"的文案括弧在 Vault 中怎么标（避免 Track 无法独立发行）

---

### 4.0 Track 1 拍板区（2026-07-14 路线图 LOCKED）

> Kieran 7-14 拍板：Track 1 路线图已锁定。Sound DNA / Suno Prompt / Lyrics SOP 仍待 Kieran 拍板。

**Track 1 关键决策（已固化）**：

- **发布日**：2026-09-11（A6 Oaeli Track 1 · 与 Luna T01 / Weini T02 同步集中推）
- **主题**：清晨 Madrid 公寓（a 孤独醒来）— 与 Aube Valois 巴黎清晨公寓形成 "Sun rise across culture" 系列
- **节奏**：先路线图，再 Sound DNA LOCKED，再 Suno Prompt，再 Lyrics，最后 Sound check + Master
- **Catalog**: `HR-A6-T01`
- **AI_DISCLOSURE**: `AI-generated music under Haevo Project`（继承自 8-ARTISTS LOCKED）

**仍待 Kieran 拍板的字段**（不擅自填写 v0.2 风格内容规划文档 / Brand Bible）：

| 决策点 | 待 Kieran 拍板 |
|---|---|
| BPM 区间 | ⚠️ 外部建议 80-95 BPM（v0.2 § 3.0.2 输入），最终区间 Kieran 定 |
| Key | ⚠️ 待 Kieran 拍板 |
| 结构 | ⚠️ 候选 Latin Pop Standard（v0.2 § 3.0.2 输入）vs 4-段 Ambient |
| 人声比 | ⚠️ 待 Kieran 拍板 |
| Suno Vocal 语种 | ⚠️ 待 Kieran 拍板（es-MX / es-ES） |
| 4×N 矩阵选 1 | ⚠️ 路线图先入"清晨 Madrid 公寓（a 孤独醒来）"，最终从 8 候选选 |
| Forbidden 名单 | ⚠️ 4 项待 Kieran 拍板（v0.1 § 2.2）|
| Reference 艺人 | ⚠️ 候选列表（v0.1 § 3.3）Kieran 拍 |
| Visual DNA | ⚠️ 摄影 vs illustration / 主色 / 主体 / tag line 待 Kieran 拍 |
| Track 1 SOP 起始日期 | ⚠️ 路线图建议 D-56 ~ D+90 SOP（参考 Weini Track 02 Playbook v0.1）|
| Lyrics Vault 接入点 | ⚠️ "Lyrics Vault vs Track 1" 衔接规则 |

---

## 5. 路线图（v0.2 wip → LOCKED 待 Kieran 拍板）

| 阶段 | 内容 | 状态 |
|---|---|---|
| v0.1（本文件）| 现有事实 + 拍板区清单 | wip |
| v0.2 | Brand Bible § 1-4（Sound 区间 / Forbidden / Business / Visual）| 待 Kieran 拍板 |
| v0.3 | Track 1 SOP 候选 4-8 段 | 待 Kieran 拍板 |
| v1.0 | Brand Bible LOCKED（参考 Weini v0.3 SPLIT 模式）| 待 Kieran 拍板 |
| v1.1 | Track 1 master + RouteNote 提交 | 待 Track 1 拍板 |

---

## 5. 拍板项清单（Kieran 决策区）

按优先级：

1. ⚠️ **Sound 层 5 项**：BPM / Key / 结构 / 人声比 / Suno Vocal 语种
2. ⚠️ **Forbidden 层 4 项**：Reggaeton / Trap / Flamenco 浓 / Old-school
3. ⚠️ **Reference Music**：3-5 位 reference 艺人锁定
4. ⚠️ **Visual DNA**：摄影 vs illustration / 主色 / 主体 / tag line
5. ⚠️ **Track 1 主题**：4 候选（室内 / 室外 / 节庆 / 都市独居）

每项需 Kieran 拍板才能进入 Brand Bible。我等待 ⚠️ 区被填。

---

## 6. 严禁项

- ❌ 不擅自写 v0.2 Brand Bible 内容（必须 Kieran 拍板）
- ❌ 不擅自生成 Sound DNA 单值（区间模式 LOCKED 7-13）
- ❌ 不擅自锁定 Lyric SOP 字段
- ❌ 不擅自定 Forbidden 层（边界敏感）
- ❌ 不擅自跑 Suno 试作（必须先 Sound DNA 区间 LOCKED）

---

## 7. 引用

- 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2 (A6 数据卡)
- 八位藝人流量權重曲風映射報告.md（Oaeli 行 + 🥉 P2 优先级）
- 30-Resources/Music-Genres/RN-Genres-39.md（RouteNote 39 主 Genre 列表，已 LOCKED）
- hky:artist-operating-system（Brand Bible vs Track Playbook SPLIT LOCKED）
- hky:multi-artist-label-playbook（parallel artist 共用 D2-T/D2-D 后端）
