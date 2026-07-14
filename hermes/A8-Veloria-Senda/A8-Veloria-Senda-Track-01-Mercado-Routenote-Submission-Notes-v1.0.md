---
title: Veloria Senda Track 01 Mercado — RouteNote 提交说明 v1.0
artist: Veloria Senda (A8)
track: T01
catalog: HR-A8-T01
version: v1.0
status: LOCKED 2026-07-14
updated: 2026-07-14
release_date: 2026-09-11
extends:
  - A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md
  - A8-Veloria-Senda-Track-01-Mercado-Release-Summary-v1.0-LOCKED.md
  - 30-Resources/Music-Genres/RN-Genres-39.md
  - 八位藝人流量權重曲風映射報告.md § Veloria Senda 行
tags: [Veloria Senda, Track 01, Mercado, RouteNote, Submission Notes, v1.0, LOCKED]
---

# Veloria Senda Track 01 Mercado — RouteNote 提交说明 v1.0（2026-07-14）

> **本文件 = D-Day RouteNote 提交手册**（Kieran 手动执行，bot-b 无凭证 LOCKED 7-13）。
> **LOCKED 红线**：bot-b 不断提交、不写 UPC/ISRC/RELEASE_DATE 入 ID3（RouteNote 分配）。
> **本文件唯一矛盾点**：Genre Primary/Secondary 终选冲突 = Kieran 拍板。

---

## §1. 提交前 checklist（bot-b 准备完毕）

| 项 | 状态 | 路径 |
|---|---|---|
| Release FLAC | ✅ LOCKED | `hermes/A8-Veloria-Senda/T01-Delivery/Mercado-Release.flac` (36.85 MB) |
| Cover PNG 3000×3000 | ✅ LOCKED | `hermes/A8-Veloria-Senda/T01-Delivery/Mercado-Cover-v1.0-3000.png` |
| ID3 Tags 28 | ✅ LOCKED | metaflac 注入完毕 |
| Cover PICTURE | ✅ LOCKED | 1 张 type=3 front cover |
| Lyrics 文本 | ✅ LOCKED | Kieran 手写 2150 char（8 段模板，100% 结构服从 A3）|
| AI Disclosure | ✅ LOCKED | ID3 含 `AI-DISCLOSURE=AI-generated` + DISCLAIMER |

---

## §2. RouteNote 必填字段（与 Oaeli 7-13 LOCKED 同集）

### 2.1 Release-level（单 Track 单曲提交）

| 字段 | LOCKED 值 | 来源 |
|---|---|---|
| **Title** | `Mercado` | TITLE LOCKED 7-14 |
| **Artist Name** | `Veloria Senda` | ARTIST tag LOCKED |
| **Featured Artist** | （空）| 单人项目 |
| **Label** | `Haevo Records` | LABEL LOCKED |
| **Catalog Number** | `HR-A8-T01` | CATALOGNUMBER LOCKED |
| **Track Title Version** | `Original Mix` | 单 Track |
| **Genre (Primary)** | `Latin` | LOCKED 7-14 全栈 |
| **Subgenre (Secondary)** | `World` | LOCKED 7-14 全栈 |
| **Release Date** | **`2026-09-11`** | 4-artist 同日 LOCKED |
| **Pre-save** | ✅ Enable | 与 Oaeli / Luna 7-13 一致 |
| **Language** | `Spanish` | RouteNote dropdown |
| **Language of Vocals** | `Spanish` | es-MX 女主 + es-PE 合唱 |

### 2.2 Distribution 字段

| 字段 | LOCKED 值 |
|---|---|
| **Tier** | **Premium $10/yr**（与 Oaeli / Luna 7-13 同）|
| **Stores** | All 35+ stores worldwide |
| **Territory** | **Worldwide** |
| **Explicit Content** | `No` |
| **Distribution Model** | `Single` |

### 2.3 ID3 Locks（不能改，RouteNote 不接 UPC/ISRC/RELEASE_DATE 入表单）

🚫 **留空**（RouteNote 分配）：
- **UPC** = RouteNote assigns
- **ISRC** = RouteNote assigns per platform
- **Barcode** = Not applicable (digital single)

---

## §3. ⚠️ Genre Primary/Secondary 冲突 LOCKED 待 Kieran 拍板

### §3.1 现状冲突（已 LOCKED 7-14 解决）
| 来源 | Primary | Secondary | 状态 |
|---|---|---|---|
| **ID3 SECONDARYGENRE**（metaflac 实装，7-14 重写）| Latin | **World** | ✅ 实测（`949ad2ed...`）|
| **Brand Bible §5.1**（vault truth）| Latin | **World** | ✓ LOCKED 7-14 |
| **v4.2 matrix**（8-artist LOCKED 7-13）| Latin | World | ✓ LOCKED |
| **HAEVO-8-ARTISTS §4.2 A8** | Latin | World | ✓ LOCKED |

### §3.2 拍板 = A LOCKED（2026-07-14）
**A — 全栈 World** LOCKED：ID3 + Brand Bible + v4.2 + HAEVO-8-ARTISTS 4 方一致。
Kieran 拍 A → bot-b 已修正 metaflac SECONDARYGENRE=Alternative → World。
Tag-on-disk MD5: `949ad2edb1f87c79b5cb0dd96391c5ac`。

### §3.3 拍板状态 = 已锁定 7-14
- [x] **A** — 全栈 World LOCKED
- [ ] B — ID3 Alternative 优先（已拒绝）
- [ ] Kieran 自定义（未启用）

---

## §4. Subtitle / Tag line / Bio 模板（LOCKED 7-14）

### 4.1 Subtitle 字段（RouteNote 表单，可选）
```
de la mañana a la carta
```
（叙事锚 = "carta a la abuela" / "amanecer de mercado" 双重钩；中文释义 = 从清晨到信）

### 4.2 Cover / Smart Link Tag line（终身 LOCKED）
```
Canta lo que se compra en el amanecer
```
（与 Oaeli "Canta lo que no se dice al despertar" 同 ROOT 跨厂牌对切）

### 4.3 Artist Bio（RouteNote Artist Profile / Spotify / Apple Music）

**英文版（350 chars / 拉丁美洲 + World target）**：
> Veloria Senda is the Andean morning market voice. She sings the horas
> of Mercado de Abastos — the spices, the handwoven textiles, the
> grandmothers placing corn into baskets. A female Latin folk project
> under Haevo Records, produced by XIAOYANG ZHANG with Suno 5.5 Pro,
> focused on Latin American everyday life through warm acoustic guitar,
> soft flutes, and intimate es-MX + es-PE vocals. Cross-cultural dawn
> storytelling: 5 languages × 5 times of day.

**西语版（400 chars / DACH 文化媒体专用）**：
> Veloria Senda es la voz del mercado en la mañana. Canta las horas del
> Mercado de Abastos en los Andes — los olores, los tejidos bordados,
> las abuelas echando maíz a la canasta. Un proyecto de folk latino
> femenino bajo Haevo Records, producido por XIAOYANG ZHANG con Suno
> 5.5 Pro, enfocado en la vida cotidiana latinoamericana a través de
> guitarra acústica cálida, flautas suaves y voces íntimas es-MX + es-PE.
> Narrativa intercultural del amanecer.

### 4.4 Genre context（Spotify Apple Editorial 提交）
> Latin Folk · Cantautor · World Music. Andean highlands. Female folk
> storyteller. Bilingual (es / en brief signature). Acoustic guitars,
> light percussion, soft flutes — no trap, no EDM, no reggaeton. Inspired
> by Natalia Lafourcade (Casa era), Lila Downs, Susana Baca, Lhasa de
> Sela, Julieta Venegas.

---

## §5. Editorial Pitch 平台清单（Latin Folk × World Music LOCKED 7-14）

### 5.1 Spotify Editorial Playlists（5+ 候选）
| Playlist | Why |
|---|---|
| **Viva Latino** | Top Latin Editorial |
| **¡Mira! Mujer** | 拉美女艺人专项 |
| **Acoustic Latin** | 拉丁民谣/原声 |
| **Café del Mar — Latin** | 早市咖啡馆场景钩 |
| **Bedroom & Folk** | 跨流派 Folk Editorial（World ↔ Bedroom）|
| **Andean Sunrise** （如存在）| Andes 高地专项 |

### 5.2 Apple Music Editorial（4+ 候选）
- Apple Music Latin America (Mexico / Argentina / Peru / Colombia)
- Apple Music Folk（World pegging）
- Apple Music Música del Mundo
- Apple Music Discovery（新人优先）

### 5.3 Deezer Editorial（3+ 候选）
- 拉美 Folk Lists
- World Music France（Lhasa de Sela 边界，France 受众共鸣）
- Editorial ES/PE/CL local

### 5.4 Tidal / Qobuz（2+ 候选）
- Qobuz Spanish Folk
- Tidal World Music Curator

### 5.5 社交媒体 4 平台（与 Weini 7-13 LOCKED 共享协议）
- Instagram（@veloria.senda）
- TikTok（账号待注册 / track teaser 30s for Pre-save）
- YouTube Shorts（fade out 风"清晨 Mercado"）
- Facebook（拉美社媒主入口，与 Luna 7-13 同 LOCKED）

---

## §6. 5-artist 24h 闭环 hashtag（提交 Cover / Smart Link 时一并用）

```
#HaevoRecords24h
```
闭合 5 语言 × 5 时段 = 1 个 label × 24 小时统一品牌叙事：

| 艺人 | 时段 | Track 1 锚 |
|---|---|---|
| A2 Lune Veya | 深夜 | Silver Eyes |
| A4 Shibata Luna | 温柔夜 | Yasashii Yoru |
| A6 Oaeli | 黄昏 | Amanecer Madrid |
| **A8 Veloria Senda** | **高地清晨** | **Mercado** |
| A5 Aube Valois | 巴黎黎明 | Premier Matin |

A8 Track 01 Mercado = 矩阵中"高地清晨"slot。

---

## §7. D-Day 时间轴（Kieran 手动执行）

| 日期 - D-Day | 任务 | 行动者 | 备注 |
|---|---|---|---|
| **D-7** = 2026-09-04 | 准备 Smart Link + Pre-save | Kieran | 用 pre-save.fm 或 DistroKid SmartLink |
| **D-3** = 2026-09-08 | RouteNote 表单提交 | Kieran 手动 | 必带：FLAC + Cover PNG + Lyrics 文 + Release Notes |
| **D-1** = 2026-09-10 | 预审 RouteNote 状态 | Kieran | 35+ 商店列表确认 |
| **D-Day** = 2026-09-11 | 全球 release 上线 | RouteNote 自动 | 9/11 4-artist 同日（Oaeli A3 / Luna T01 / Weini T02 + Veloria A8 T01）|
| **D+1** = 2026-09-12 | Apple Music / Spotify 验证 | Kieran | 听首日播放 + Editorial 搜索 |
| **D+7** = 2026-09-18 | Save Rate 评估 | Kieran + bot-b 报告 | 写入 Brand Bible §10 |
| **D+30** = 2026-10-11 | Editorial Playlist 命中率 | Kieran | 写入 Brand Bible §10 |
| **D+90** = 2026-12-10 | Sound DNA 区间是否调整 | Kieran + bot-b | 写入 Brand Bible §10 |

---

## §8. ⚠️ Honest disclosure

| 局限 | 影响 | 缓解 |
|---|---|---|
| ID3 `SECONDARYGENRE=Alternative` vs Brand Bible `World` 不一致 | 待 Kieran 拍 §3 | 默认选项 A 全部对齐 World |
| 4-artist 同日 9/11 上线，RouteNote 是否拆 profile | 多个 artist profile 防止算法权降权 | 4 厂牌子 Profile LOCKED 7-13 |
| Editorial Playlist ID 不可能在 bot-b VPS 验证 | 提交候选纯文本，Kieran 在 suno/Spotify for Artists 验证 | 与 Oaeli A3 同 LOCKED 7-13 |
| Genre 39-list 在锁定期间可能 RouteNote 更新 | 提交前再看 RN-Genres-39-LOCKED 档 | 7-13 LOCKED 文档治理 |
| **UPC/ISRC/RELEASE_DATE 在 ID3 中留空** | RouteNote 必填时自动分配 | LOCKED 7-13 直接继承 |

---

## §9. 引用

- A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md（永久 + §5.1 Genre LOCKED）
- A8-Veloria-Senda-Track-01-Mercado-Release-Summary-v1.0-LOCKED.md（Release FLAC）
- A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md
- 30-Resources/Music-Genres/RN-Genres-39.md
- 八位藝人流量權重曲風映射報告.md
- 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2
- A6-Oaeli/Style-Content-Plan-v0.2.md（量质分工 LOCKED）
- multi-artist-label-playbook §"5-artist 24h 闭环"
- multi-artist-label-playbook §"v4.2 Genre matrix LOCKED"

---

## ⚠️ 当前未拍：§3.3 Genre 拍板

**LOCKED 候选 = A**（全栈对齐 World）。Kieran 选 1/2/3 后推进 ID3 修正 + 提交。
