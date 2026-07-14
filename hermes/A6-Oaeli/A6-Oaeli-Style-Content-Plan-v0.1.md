---
title: Oaeli 风格内容规划 v0.1
version: v0.1
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

## 3. 内容规划方向（v0.1 WIP）

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

- ⚠️ 室内（清晨 Madrid 公寓）：与 Aube Valois（巴黎清晨）形成 Parallel
- ⚠️ 室外（白天海边）：西班牙向海性
- ⚠️ 节庆（Semana Santa / La Tomatina）：文化锚定
- ⚠️ 都市独居（一居室 23:00）：与 Luna （夜晚 Tokyo）/ Weini（夜晚台北）形成跨厂牌横切

---

## 4. 路线图（v0.1 WIP → LOCKED 待 Kieran 拍板）

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
