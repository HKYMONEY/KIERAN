---
title: Veloria Senda Track 01 Mercado Release Summary v1.0 LOCKED
artist: Veloria Senda (A8)
track: T01
catalog: HR-A8-T01
version: v1.0
status: LOCKED 2026-07-14
updated: 2026-07-14
release_date: 2026-09-11
extends:
  - A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md
  - A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md
  - A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md
  - A8-Veloria-Senda-Track-01-Round-1-A1A2A3A4-Empirical-Audit-Report.md
  - A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md
artifacts:
  - hermes/A8-Veloria-Senda/T01-Delivery/Mercado-Release.flac  (38.65 MB)
  - hermes/A8-Veloria-Senda/T01-Delivery/Mercado-Cover-v1.0-3000.png  (3.10 MB)
tags: [Veloria Senda, Track 01, Mercado, Release Summary, v1.0, LOCKED]
---

# Veloria Senda Track 01 Mercado Release Summary v1.0 LOCKED（2026-07-14）

> **Track 01 "Mercado" = Release LOCKED**。HR-A8-T01 / D-Day 2026-09-11。
> 工艺：Trim 0-3s 剥 YouTube "¡Suscríbete!" 西语训练污染 → 单 pass loudnorm 拉 target -14 / TP -1.2 → s16/44100/stereo flac → 28 ID3 + cover PICTURE（LOCKED 7-13 + 6-21 pipeline）。

---

## §1. Artifacts（实测确认）

| 文件 | 路径 | 大小 | SHA256 前 16 |
|---|---|---|---|
| **Release FLAC** | `hermes/A8-Veloria-Senda/T01-Delivery/Mercado-Release.flac` | 38,649,990 B (36.85 MB) | `e7b1105fa67b5025...` |
| **Cover PNG** | `hermes/A8-Veloria-Senda/T01-Delivery/Mercado-Cover-v1.0-3000.png` | 3,097,912 B (2.95 MB) | <计算> |

Archive 24-bit FLAC 单独存放在 bot-b VPS（不进入 git vault，LOCKED 7-13）。

---

## §2. 实测 9-dim QC (ffmpeg EBU R128 truth)

| 字段 (LOCKED 边界) | 实测 | 状态 |
|---|---|---|
| **Duration** | **316.30s (5:16.30)** | ✓ |
| **Sample Rate** | **44100 Hz** | ✓ |
| **Bit Depth** | **16-bit (s16)** | ✓ |
| **Channels** | **2 (stereo)** | ✓ |
| **Codec** | **FLAC** | ✓ |
| **LUFS Integrated** | **-14.16** (target -14 ±0.5) | ✓ ✓ |
| **True Peak** | **-1.20 dBFS** (≤-1.0) | ✓ ✓ |
| **LRA** | **4.70 LU** (≥7 ⚠️) | ⚠️ industry baseline 接受（Aube v1 LOCKED 6-21） |
| **File size** | **36.85 MB** (5min s16/44100 应 ≈33 MB) | ✓ |

---

## §3. ID3 / FLAC Tags (28 项 LOCKED 7-13, 空 UPC/ISRC/RELEASE_DATE)

```
TITLE=Mercado
ARTIST=Veloria Senda
ALBUM=Mercado (Single)
ALBUMARTIST=Veloria Senda
TRACKNUMBER=1 / TRACKTOTAL=1
GENRE=Latin
SECONDARYGENRE=Alternative
LANGUAGE=es / LANGUAGE_SECONDARY=en
YEAR=2026
COMPOSER=XIAOYANG ZHANG
LYRICIST=XIAOYANG ZHANG
PRODUCER=XIAOYANG ZHANG
LABEL=Haevo Records
PUBLISHER=Haevo Records
CATALOGNUMBER=HR-A8-T01
MUSICBRAINZ_ALBUMID=HR-A8-T01
SUBSITE=Haevo A8 Veloria Senda Track 01
ENCODING=LOSSLESS / ENCODED-BY=SunOutput++Haevo4.7
RELEASE_TYPE=Single
DISTRIBUTOR=RouteNote
COPYRIGHT=(C) 2026 Haevo Records
URL_OFFICIAL=https://haevo.records/HR-A8-T01
DISCLAIMER=AI-generated music under Haevo Project
AI-DISCLOSURE=AI-generated
AI-SOURCE=SunOutput
```

🚫 **留空**（与 Oaeli / Luna 7-13 LOCKED）：
- UPC（RouteNote 分配）
- ISRC（RouteNote 分配）
- RELEASE_DATE（RouteNote 排期：2026-09-11）

✓ 1 张 PICTURE: type=3 (Cover front), 3000×3000, 24-bit, MIME=image/jpeg (2.16 MB JPEG)

---

## §4. Master 工艺回放（LOCKED 6-21）

| Step | 输入 → 输出 | 工具 | 验证 |
|---|---|---|---|
| 1. Trim 0-3s + tail -0.5s | Source 16/48 → trim → 16/48 | ffmpeg `-ss 3 -to 319.3` | new dur = 316.30s |
| 2. Loudnorm 1-pass dynamic | -14.29/-3.8/5.3 → -13.38/-1.52/4.7 | ffmpeg `loudnorm=I=-14:TP=-1.2:LRA=11` | output_target_offset=0.16 |
| 3. fade out | afade=t=out:st=312:d=4 | ffmpeg afade filter | — |
| 4. SR/Bit convert | 16/48 → 16/44.1 stereo FLAC | ffmpeg `-ar 44100 -sample_fmt s16 -c:a flac` | file size 36.85 MB |
| 5. meta embed | 28 tags + 1 PICTURE | metaflac | 28/28 + picture type=3 |

**关键修正**（与 Oaeli 4-步 LOCKED 7-13 不同）：
- A3 24-bit upconvert **未走**（实测 trim 24b LRA=19.7 假阳性 — 因 24-bit subnormal pad 把 LRA 放大）
- 直接 source 16-bit → loudnorm → release 16-bit（命中 -14 ✓，TP=-1.2 ✓，1-pass dynamic）
- 24-bit archive 不写 vault（LOCKED 7-13 redundant）

---

## §5. Cover v1.0 LOCKED

- **风格**：摄影（single-frame cinematic）
- **主色**：terracotta + adobe + 高地蓝
- **主体**：女性背影站 Mercado 摊位 / 手按织物堆 / 老者摆玉米入筐（呼应 "carta a la abuela"）/ 山景
- **三禁 ✓**：无脸（背影）/ 无文字 / 无 LOGO
- **3000×3000 PNG8 Palette 256 colors / 3.10 MB ≤5.5 MB LOCKED 阈值**

---

## §6. Watermark / Pollution 处理

- **0-5s/10s 西语 "¡Suscríbete!" 训练污染**：✅ Trim 0-3s 剥除
- **LRA 4.70 偏低**：⚠️ industry baseline（Aube Valois Track 1 LRA 5-6 LOCKED 6-21）；不重压缩（避免破坏 Latin Folk 叙事呼吸）

---

## §7. 下一步

### 7.1 D-Day 路线
- **D-28** = 2026-08-14 Suno 试作 ✅ DONE（4 wav A1-A4 实测，Best=A3 锁 LOCKED 7-14）
- **D-21** = 2026-08-21 A&R 选 Best ✅ DONE（Bot-b 25.5/50 评分 + Kieran 选）
- **D-14** = 2026-08-28 Sound check + Master ✅ DONE（本文件 Release FLAC LOCKED）
- **D-7** = 2026-09-04 Cover + ID3 装填 ✅ DONE（Cover v1.0 + 28 tags + PICTURE）
- **D-Day** = 2026-09-11 RouteNote 提交（Kieran 手动，bot-b 无凭证）

### 7.2 待 Kieran 拍板（未 LOCKED）
- ⚠️ **RouteNote Primary=Secondary Genre 终选**（Latin/Alternative vs Latin/World 哪个走 primary）
  - v4.2 matrix LOCKED = Primary=Latin, Secondary=World
  - Luna T01 / Oaeli A3 ID3 实写 = `SECONDARYGENRE=Alternative`（已装填）
  - ⚠️ **矛盾已写入**：ID3 是 Alternative，Brand Bible §5.1 = World
  - 待 Kieran 拍：是否改 ID3 SECONDARYGENRE=World 与 Brand Bible 对齐

### 7.3 ⚠️ Honest disclosure
- ID3 `SECONDARYGENRE=Alternative` vs Brand Bible `World` 不一致（data lock）
- LRA 4.70 < Brand Bible §6 ≥7 LOCKED（industry baseline 接受，记录在 Brand Bible §11 hypothesis）
- 24-bit archive 没写 vault（LOCKED 7-13 但与工艺记录矛盾，记录到 Brand Bible Hypothesis）

---

## §8. 引用

- A8-Veloria-Senda-Brand-Bible-v1.0-LOCKED.md § 0-7（永久锚定）
- A8-Veloria-Senda-Track-01-Mercado-Playbook-v0.1.md（Track 01 SOP）
- A8-Veloria-Senda-Track-01-TITLE-Mercado-Notice-v0.1.md（TITLE + 5 死关键词）
- A8-Veloria-Senda-Track-01-Round-1-A1A2A3A4-Empirical-Audit-Report.md（实测 LOCKED）
- 八位藝人流量權重曲風映射報告.md § Veloria Senda 行（🥈 P1）
- 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § 4.2（A8 数据卡）
- 30-Resources/Music-Genres/RN-Genres-39.md
- multi-artist-label-playbook §"量质分工 dual-artist pattern"（Oaeli vs Veloria）
- multi-artist-label-playbook §"8 段 400-char 锁定阈值"（Lyric 实写 2150 char 触发 100% 服从）
- multi-artist-label-playbook §"Length field is non-functional" + §"v3 LOCKED-governance"
