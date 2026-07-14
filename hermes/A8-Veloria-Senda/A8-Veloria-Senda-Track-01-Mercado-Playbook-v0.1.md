---
title: Veloria Senda Track 01 — Mercado 早市 Playbook v0.1
artist: Veloria Senda (A8)
track: T01
catalog: HR-A8-T01
version: v0.1
status: wip (LOCKED 2026-07-14)
updated: 2026-07-14
release_date: 2026-09-11
extends:
  - A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md § 0-7
tags: [Veloria Senda, Track 01, Mercado, Playbook, v0.1, wip]
---

# Veloria Senda Track 01 — Mercado 早市 Playbook v0.1

> **本文件 = Fast Iteration 层（multi-artist-label-playbook #3）**。Track 01 单独 SOP，发布后归档。
> **主题 LOCKED**：拉美山地小镇 Mercado de Abastos 拂晓（与 Aube "Premier Matin" 巴黎清晨公寓 / 微霓 "窓辺" 室内外 跨厂牌清晨主题矩阵 LOCKED 7-14）。

---

## §1. Track Metadata

| 字段 | LOCKED |
|---|---|
| **TITLE** | TBD（建议候选：Mercado / Carta para abuela / Antes del amanecer）⚠️ 待 Kieran 拍板 |
| **Catalog** | **HR-A8-T01** |
| **Release** | **2026-09-11**（与 Luna T01 / Weini T02 / Oaeli T01 同日 4-artist release）|
| **Duration** | **3:40-4:10**（区间 LOCKED，Brand Bible §5.3）|
| **Language Tag ID3** | `es / es-MX, es-PE, es-CL`（区间 Latin Folk 池）|
| **Genre ID3** | `Latin` |
| **Secondary ID3** | `World` |
| **Subgenre ID3 multi-value** | `Latin Folk;World Music;Cantautor` |

---

## §2. Sound DNA（Track 01 应用）

| 字段 | Track 01 LOCKED |
|---|---|
| **BPM** | **98 BPM**（区间 90-108 内，市场早市人潮节奏）|
| **Key** | **D Dorian**（区间 Dorian 锁单值）|
| **传统乐器** | **30%（泛化描述）** → Prompt 写 "warm acoustic guitar, light Latin percussion, soft flutes"（不点名 Charango/Quena/Cajón）|
| **人声比** | **70% Female (es-MX) + 30% Male Chorus (es-PE)** |
| **Suno Vocal** | **Vocal Female + Vocal Male 双 vocalist** |
| **Style Influence** | **75%** |
| **Weirdness** | **15%** |

---

## §3. Lyric SOP v1.0（Track 01 套用）

### 3.1 字符预算
- **总长**：**550-700 chars**（8-segment 模板，E4 v1.5 LOCKED 6-21）
- **段落预算**：[Intro] 30 + [Verse 1] 80 + [Pre-Chorus] 60 + [Chorus] 80 + [Verse 2] 80 + [Bridge] 80 + [Instrumental Break] 30 + [Outro] 50 ≈ 590 chars ✓

### 3.2 8-Segment 模板（Latin Folk 应用）

```
[Intro]
(instrumental warm acoustic guitar y light percussion, 8 compases)

[Verse 1]
<Tema Mercado: amanecer en mercado de abastos andino, 4 líneas octosílabos>
<ánimo: alegría compartida + nostalgia por abuela ausente>

[Pre-Chorus]
<tensión emocional: escribir carta a la abuela, 4 líneas>
<rima AABB, mismo scheme>

[Chorus]
<core hook — frase ancla + 4 líneas>
<TITLE aparece aquí>

[Verse 2]
<segunda escena: los puestos, olores, sonidos, 4 líneas>
<mismo narrative anchor = carta a la abuela>

[Pre-Chorus]
<segunda pasada, mismo texto>

[Chorus]
<segunda pasada>

[Bridge: voz más íntima, casi susurro con guitarra sola]
<nueva perspectiva: la abuela respondería, 4 líneas>
<timbre shift = Suno trigger Bridge 100% LOCKED>

[Instrumental Break: percusión suave y flauta andina]
<interludio textural 8-12s>

[Chorus]
<final chorus = entregada emocional máxima>

[Outro: fade out largo, 8 compases, guitarra y voz desvaneciéndose]
<4s afade post-producción necesario>
```

### 3.3 押韵 LOCKED
- **AABB 严押韵**（Latin Folk romancero 传统）
- **8 音节 / 行**（octosílabo）
- **段尾回归** = 4 段共用同 rhyme scheme

### 3.4 语言比
- **es 95% + en 5%**：en 仅写 **"for grandmother, from the Andes"** 类末行落款
- **不用** Quechua / Nahuatl 词缀（Track 6+ 再开）

---

## §4. Suno Prompt v0.1（Track 01 候选）

**KEY DISCOVERY（locked 6-21）**：Lyrics 字段必须 ≥400 chars 触发 Suno 8-段结构服从。

### 4.1 Title 字段
```
TBD — Track 01 待 Kieran 拍板
候选：A. "Mercado" / B. "Carta para abuela" / C. "Antes del amanecer"
```

### 4.2 Style of Music 字段
```
Warm Latin folk ballad, organic acoustic guitar, light Latin percussion, soft flutes,
intimate female vocal (Spanish es-MX), warm male chorus harmonies,
morning market atmosphere, sunrise ambience, organic and earthy production,
Audeo L4 CD -16 LUFS, no trap, no EDM, no reggaeton, no tropical,
98 BPM, D Dorian.
```

### 4.3 Lyrics 字段（占位，Track 1 实际生成）
- v0.1 占位 = 8-segment 模板 + Brand Bible §3.1-3.4 语言 LOCKED 边界
- 实际写词 = **Kieran 手写 / 委外 / Suno 内 lyric 模式 自选**（待 Kieran 拍板）

### 4.4 Exclude Style 字段（label-wide v1.1 patch + Veloria Senda specific）
```
weird, weirdness, stylized influence,
trap, EDM, reggaeton, salsa, cumbia, merengue,
banda, norteño, corridos, mariachi,
tropical, descarga,
weird, weird, weird, dubstep, psytrance
```

---

## §5. Visual / Cover 协议

详见 Brand Bible §1

### 5.1 Cover 主线 LOCKED
- **风格**：摄影（single-frame cinematic）
- **主色**：terracotta + adobe + Andes 高地蓝
- **主体**：女性背影站 Mercado 摊位 / 手持辣椒或织物 / 木箱拖地声隐喻
- **Tag line 入 Subtitle / Bio** = "Canta lo que se compra en el amanecer"

### 5.2 Cover 工具候选
- Ideogram 2.0（西班牙语文字支持 / 免费 50/天）
- Midjourney（无文字，**适合 Veloria 美学** 因为 Tag line 不入画面）
- Flux $20/月（备选）

---

## §6. Mastering / FLAC 协议

| 字段 | LOCKED |
|---|---|
| **Master 工艺** | 4 步（与 Oaeli 同 7-13 LOCKED）|
| 1. Suno source → 24-bit archive | upconvert 48→24 keep length |
| 2. Loudnorm | Stage 2 1-pass linear target=-14 LUFS / TP=-1.0 |
| 3. Downconvert → Release | 16-bit / 44.1 kHz / flac |
| 4. 实测 QC | 7 维 + Forbidden check + Whiper multi-window |

### 6.1 7 维 QC（每项实测）
1. Duration（区间 3:40-4:10）
2. LUFS Integrated（target -14 ±0.5）
3. True Peak（≤-1.0 dBFS）
4. LRA（≥7 LU）
5. Bit / SR（16-bit / 44.1 kHz）
6. Forbidden check（YouTube watermark / Amara 等）
7. Whisper multi-window 结构服从率（≥80%）

---

## §7. ID3 / FLAC Tags v0.1（待 Master 后实写）

```
TITLE=Mercado (TBD Track 1 title)
ARTIST=Veloria Senda
ALBUM=Mercado (Single)
ALBUMARTIST=Veloria Senda
TRACKNUMBER=1 / TRACKTOTAL=1
GENRE=Latin
SECONDARYGENRE=World
LANGUAGE=es / LANGUAGE_SECONDARY=en (es 95% + en 5%)
YEAR=2026
COMPOSER=XIAOYANG ZHANG
LYRICIST=XIAOYANG ZHANG
PRODUCER=XIAOYANG ZHANG
LABEL=Haevo Records
PUBLISHER=Haevo Records
CATALOGNUMBER=HR-A8-T01
MUSICBRAINZ_ALBUMID=HR-A8-T01
SUBSITE=Haevo A8 Veloria Senda Track 01
ENCODING=LOSSLESS
ENCODED-BY=SunOutput++Haevo4.7
RELEASE_TYPE=Single
DISTRIBUTOR=RouteNote
COPYRIGHT=(C) 2026 Haevo Records
URL_OFFICIAL=https://haevo.records/HR-A8-T01
DISCLAIMER=AI-generated music under Haevo Project
AI-DISCLOSURE=AI-generated
AI-SOURCE=SunOutput
```

**🚫 留空**（与 Oaeli 同 7-13 LOCKED）：
- UPC（RouteNote 分配）
- ISRC（RouteNote 分配）
- RELEASE_DATE（7-13 LOCKED → RouteNote 排期）
- Barcode（同 UPC）

---

## §8. D-Day 时间轴（Kieran 拍板 LOCKED 路线）

| 日期 | 阶段 | 行动 |
|---|---|---|
| **D-28** = 2026-08-14 | Suno 试作 | Kieran 在 suno.com 跑 Track 01，3-5 wav 候选 |
| **D-21** = 2026-08-21 | A&R 选 Best | bot-b 实测 4 件 + Kieran 听感拍 |
| **D-14** = 2026-08-28 | Sound check + Master | 4 步 Mastering + 7 维 QC |
| **D-7** = 2026-09-04 | Cover + ID3 装填 | 摄影 + upscale 3000×3000 + 28 ID3 tags |
| **D-Day** = 2026-09-11 | RouteNote 提交 | Kieran 手动提交（bot-b 无凭证）|

---

## §9. 拍板项清单（Track 01 入 Suno 前必拍）

1. ⚠️ **TITLE**（候选 A/B/C）
2. ⚠️ **Lyrics 字段实际写法**（Kieran 手写 / Suno 内 lyric 模式 / 委外）
3. ⚠️ **Cover 选 N 候选**
4. ⚠️ **D-28 试作确认**（Kieran 进入 suno.com + 跑 3-5 wav）
5. ⚠️ **Title 字段中的 5 死关键词**（Suno 自动替换艺人名，参考 Aube Valois 5 死关键词 LOCKED）

---

## §10. 与 A6 Oaeli 量质分工对齐

- **A6 Oaeli 量**：高频（每月 1-2 首）+ Latin Pop 模板 + 都市拂晓（Madrid 公寓）
- **A8 Veloria Senda 质**：低频（每季度 1 首）+ Latin Folk 精制 + 山地拂晓（Mercado）

**跨厂牌横切 LOCKED**：Track 01 Mercado 早市 ≠ Oaeli Amanecer Madrid
- 同主题（拂晓）+ 同语言（es）+ 同时段（清晨）但地理不同（高地 vs 都市）
- 共享封面系列（可后期设计 joint visual treatment）

---

## §11. 引用

- A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md（A8 永久锚定）
- 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2
- 八位藝人流量權重曲風映射報告.md
- multi-artist-label-playbook §"8 段 400-char 锁定阈值"
- multi-artist-label-playbook §"量质分工 dual-artist pattern"
