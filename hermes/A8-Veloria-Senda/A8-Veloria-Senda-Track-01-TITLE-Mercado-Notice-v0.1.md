---
title: Veloria Senda Track 01 — TITLE 拍板 = Mercado
artist: Veloria Senda (A8)
track: T01
catalog: HR-A8-T01
version: v0.1
status: wip
updated: 2026-07-14
title_locked: Mercado
extends:
  - A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md § 0
  - A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md § 1
tags: [Veloria Senda, Track 01, Mercado, TITLE LOCKED, v0.1]
---

# Veloria Senda Track 01 — TITLE 拍板 = Mercado（2026-07-14）

> **Kieran 拍板 LOCKED**：A8 Track 01 TITLE = `Mercado`
> 备选 "Carta para abuela" / "Antes del amanecer" 暂未用。
> 本文件 = TITLE 决策记录 + Suno Prompt 字段更新 + ID3 TAG 应用 + 5 死关键词。

---

## §1. TITLE 决策记录

| 选项 | 候选 | 拍板 |
|---|---|---|
| A | **Mercado** | ✅ LOCKED |
| B | Carta para abuela | （备存，可作 Subtitle 候选） |
| C | Antes del amanecer | （备存） |

### 1.1 拍板理由（bot-b 推断 + Kieran 直觉 LOCKED）
- "Mercado" = 单名词，**最简洁最强记忆点**（与 Oaeli "Amanecer Madrid" 双词名 / Aube "Premier Matin" 双词名 形成**对比**）
- 直接命中主题锚（拉美早市），无抒情 polish
- ID3 TITLE 字段 ≤ 80 chars 限制 0 风险
- Suno 5 死关键词（艺人 auto-replace 触发词）= 全空，"Mercado" 不会被 auto-replace

---

## §2. Suno Prompt 字段应用（Track 01 v0.2 更新）

### 2.1 Title 字段
```
Mercado
```

### 2.2 5 死关键词（防 Suno auto-replace）
Suno 5.5 Pro 训练集中**会被自动替换**的艺术家 / 厂牌名（参考 Aube Valois 5 死关键词 LOCKED）：
- ❌ Natalia Lafourcade
- ❌ Lila Downs
- ❌ Lhasa de Sela
- ❌ Susana Baca
- ❌ Julieta Venegas

**应用方式**：Track 01 Suno Prompt 中**不写这 5 个名字**作为参考艺术家；改写为风格泛化词（"warm Latin folk female vocal" / "intimate Mexican folk ballad"）。

### 2.3 Style of Music 字段（带 Mercado 主题锚）
```
Warm Latin folk ballad about a morning market in the Andes,
organic acoustic guitar, light Latin percussion, soft flutes,
intimate female vocal (Spanish es-MX), warm male chorus harmonies,
sunrise market atmosphere, organic and earthy production,
98 BPM, D Dorian, no trap, no EDM, no reggaeton, no tropical,
nostalgic letter to absent grandmother.
```

### 2.4 Lyrics 字段（占位）
- v0.1 占位 = 8-segment 模板（详见 `A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md` §3.2）
- TITLE = "Mercado" 应在 [Chorus] 字段出现 ≥ 2 次（参考 Aube E4 v1.5 chorus hook 模式 LOCKED 6-21）

### 2.5 Exclude Style 字段（label-wide v1.1 + Veloria Senda specific）
```
weird, weirdness, stylized influence,
trap, EDM, reggaeton, salsa, cumbia, merengue,
banda, norteño, corridos, mariachi,
tropical, descarga,
dubstep, psytrance
```

---

## §3. ID3 / FLAC Tags 应用（TITLE 更新后）

```
TITLE=Mercado
ARTIST=Veloria Senda
ALBUM=Mercado (Single)
ALBUMARTIST=Veloria Senda
TRACKNUMBER=1 / TRACKTOTAL=1
GENRE=Latin
SECONDARYGENRE=World
SUBGENRE=Latin Folk;World Music;Cantautor
LANGUAGE=es
LANGUAGE_SECONDARY=en
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

🚫 留空（与 A6 / Luna 7-13 LOCKED 同）：
- UPC（RouteNote 分配）
- ISRC（RouteNote 分配）
- RELEASE_DATE（RouteNote 排期）

---

## §4. 拍板项清单更新（Playbook §9 收缩）

| # | 拍板项 | 状态 |
|---|---|---|
| 1 | **TITLE** | ✅ **Mercado** LOCKED |
| 2 | **Lyrics 字段实际写法** | ⚠️ 待 Kieran 拍板（手写 / Suno 内 lyric 模式 / 委外）|
| 3 | **Cover 选 N 候选** | ⚠️ 待 Kieran 拍板 |
| 4 | **D-28 试作确认** | ⚠️ 待 Kieran 拍板（2026-08-14 Kieran 进 suno.com 跑 3-5 wav）|
| 5 | **Title 字段中的 5 死关键词** | ✅ LOCKED（本文件 §2.2） |

3 项仍 ⚠️。

---

## §5. 引用

- A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md § 0
- A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md § 1
- A5-Aube-Valois-Sound-DNA-v1.0-LOCKED.md §"5 死关键词"（参考 LOCKED 6-21）
- multi-artist-label-playbook §"8 段 400-char 锁定阈值"
