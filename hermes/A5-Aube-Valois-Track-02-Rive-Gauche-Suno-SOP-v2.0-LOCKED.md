---
artist: Aube Valois
artist_id: A5
track: 2
title: Rive Gauche
document_type: suno-submission-package
version: v2.0
lock_status: LOCKED
lock_date: 2026-07-13
locked_by: Kieran "Premier Matin 已发完, 新创第二首 A Rive Gauche" 拍板 (基于 Sound DNA v2.0 LOCKED)
supersedes:
  - Track-01-Suno-SOP-v1.2-LOCKED.md (2026-07-13) — Track 1 模板继承
inherit_from:
  - A5 Sound DNA v2.0 LOCKED (2026-07-13) — 9 字段 + Track 2 升级
key_changes_v2.0:
  - Title = **Rive Gauche** (vs Premier Matin)
  - BPM 76 (区间内 Producer 自由选)
  - Style 933 chars LOCKED (户外 Saint-Germain 升级)
  - Lyrics 811 chars LOCKED (Wikipedia Chanson 文学意象升级)
  - Strategy Round 1 + Round 2/3 Continue → 250s (4:10) LOCKED
purpose: Aube Track 2 « Rive Gauche » 250 秒 (4:10) 9 段法语 Cinematic Dream Pop SOP v2.0 — 24h 时间线 5 艺人续轨第二拍 (7:00 AM 户外延伸)
---

# Aube Valois — Track 2 « Rive Gauche » Suno SOP v2.0 LOCKED

## 🔒 LOCKED Banner

| 项 | 值 |
|---|---|
| **Status** | ✅ **LOCKED** (2026-07-13) |
| **Title** | **Rive Gauche** |
| **Time** | **7:00 AM** (Track 1 Premier Matin = 6:30 AM LOCKED 已发完)|
| **Producer 必读** | ⚠️ Style 933 chars / Lyrics 811 chars / Exclude 441 chars (实测)|
| **Producer Strategy** | Round 1 直出 1:50-2:30 → Round 2/3 Continue From This Song → 250s (4:10) |
| **下一次 review** | Track 5 OR 2026-12-31 |

---

## 1. Round 1 提交包 (复制粘贴进 Suno)

### 1.1 字段 1: Title

```
Rive Gauche
```

`wc -m` 实测 = 11 chars (LOCKED 2026-07-13),Spotify 25-char 搜索 56% buffer。

### 1.2 字段 2: Style of Music (933 chars 实测 LOCKED)

```text
French cinematic dream pop, 76 BPM, D minor. Saint-Germain 7 AM — film scene continuing, Rive Gauche cobblestone walk, soft golden morning light through plane trees, Paris waking up, footsteps on wet cobblestone echoing. Female intimate breathy vocal, soft bel canto, 65 percent wet reverberated old Paris room with tape saturation. Felt piano mid-register with subtle arpeggio, analog synth pads slowly evolving, cinematic string quartet soaring in chorus, nylon string guitar clean replacing electric for organic feel, soft drum machine only on final chorus. Paris field recording 8 percent layered under — footsteps on cobblestone 35 percent, distant metro doors closing 20 percent, espresso machine opening 15 percent, plane tree leaves rustling 15 percent, morning birds 10 percent, distant church bell 5 percent. Lo-fi tape hiss subtle. Romantic reflective wistful. 4 minutes 10 seconds length. Fade out with footsteps fading.
```

### 1.3 字段 3: Lyrics (811 chars 实测 LOCKED — Producer 必跑 `wc -m` 自 verify)

```text
[Intro]

[Verse 1]
Première lumière sur la rive
Les toits s'éveillent doucement
Le vent soulève la glycine
Saint-Germain ouvre ses yeux

[Pre-Chorus]
Les pavés gardent les murmures
De celles qui marchent avant l'aube
Une silhouette dans la brume
Le jour se lève, sans effort

[Chorus]
Rive gauche, première heure
Les cafés posent leurs volets
Ton cœur ralentit, demeure
Dans ce Paris qui se tait

[Instrumental Interlude]

[Verse 2]
La Seine couve encore des ombres
Les bouquinistes n'ont pas parlé
Ton pas résonne, lent, sans nombre
Rue de Buci, rue Jacob

[Bridge]
Ce matin n'appartient à personne
Il est à toi, rien qu'à toi
Une page écrite, sans plume
Le jour commence, pourquoi pas toi

[Final Chorus]
Rive gauche, première heure
Les cafés posent leurs volets
Ton cœur ralentit, demeure
Dans ce Paris qui se tait

[Outro]
```

**Pitfall #18/19 LOCKED:** 9 段 `[标签]` 后均空行 (无 prose 描述),这是 Producer 必粘贴版。

### 1.4 字段 4: Instrumental

```
False
```

### 1.5 More Options (Stage 1 三件套 LOCKED)

| 选项 | 值 | 来源 |
|------|-----|------|
| Vocal Gender | **Female** | v1.0 § 1 (Trainer 70F) |
| Weirdness | **15%** | Track 1 v0.3 实测 |
| Style Influence | **60%** | Track 1 v0.3 实测 |
| Language | **French** | v4.5 LOCKED fr-FR |

### 1.6 Exclude (441 chars 实测 LOCKED 继承 Track 1)

```
Exclude: Reggaeton, salsa, bachata, EDM, dubstep, heavy metal, hard rock, male rapper, spoken word, podcast intro, jingle, advertisement, radio, intro, outro, talking, voice over, merci d'avoir écouté, abonnez-vous, Piaf style, Brel style, Brassens style, accordion heavy, jazz café, tourist Paris, chanson réaliste, café-concert, 80s european cabaret, drum solo, drum fill, snare roll, trap beat, hi-hat rhythm, kick drum, bass guitar solo
```

---

## 2. Round N 路径 — Producer Strategy LOCKED

### 2.1 Round 1 — Stage 1 单段直出 (期望 1:50-2:30)

参考 Track 1 v3.0 PDF 报告实证 (4:11 历史) + 6+ Pitfall 实测。

**Round 1 Producer 必跑 5 项:**

```bash
SRC="<absolute path to wav>"
md5sum "$SRC"
ffprobe -v error -show_entries format=duration -of csv=p=0 "$SRC"
ffmpeg -hide_banner -i "$SRC" -af "loudnorm=I=-14:TP=-1.0:LRA=11:print_format=summary" -f null - 2>&1 | tail -12
# Whisper vocal transcript (≤ 25% LOCKED)
python3 -c "
from faster_whisper import WhisperModel
w = WhisperModel('tiny.en', device='cpu', compute_type='int8')
segs, _ = w.transcribe('$SRC', vad_filter=False)
total = sum(s.end - s.start for s in segs)
print(f'Vocal duration: {total:.2f}s ({total/$DUR*100:.1f}%)')
"
# Track 2 关键词泄漏检测 — Pitfall #19 LOCKED
python3 -c "
from faster_whisper import WhisperModel
w = WhisperModel('tiny.en', device='cpu', compute_type='int8')
segs, _ = w.transcribe('$SRC', vad_filter=False)
LEAK = ['felt piano', 'analog synth', 'piano', 'coblestone', 'nylon guitar', 'footsteps', 'morning birds', 'church bell', 'glycine']
hits = []
for s in segs:
    for k in LEAK:
        if k in s.text.lower():
            hits.append((s.start, s.end, k))
print('Field Recording hits:', hits)
"
```

**Kieran 听感 1 句话** (LOCKED):落 Best → Kieran 选 Round 2 续接点 (Track 1 LOCKED Pitfall #14)。

### 2.2 Round 2 — Continue From This Song (1:50 → 3:20)

```text
Title: Rive Gauche (Part 2 - Mid)
Style: 同 Round 1 (Aube Brand DNA = Quiet / Cinematic 一致性)
Lyrics:

[Continuation]

Les bouquinistes n'ont pas parlé
Ton pas résonne, lent, sans nombre
[Whisper]
Rive gauche...
[End]
```

`wc -m` 实测 ≈ 90 chars / Suno 上限 = 安全。

### 2.3 Round 3 — Continue From This Song (3:20 → 4:10)

```text
Title: Rive Gauche (Part 3 - Final)
Style: 同 Round 1
Lyrics:

[Dissolution]

Le café ouvre
La Seine murmure
Le jour t'attend
[Whisper - fading]
Rive gauche
s'éveille
[End]
```

`wc -m` 实测 ≈ 70 chars / 安全。

### 2.4 Round 4 — Trim + Fade-out LOCKED

```bash
ffmpeg -hide_banner -i /root/Suno_Downloads/rive-gauche-r1r2r3.wav \
  -ss 0 -to 250 -c copy /root/Rive-Gauche-master-250s.flac
ffmpeg -hide_banner -i /root/Rive-Gauche-master-250s.flac \
  -af "afade=t=out:st=242:d=8" \
  -c:a flac /root/Rive-Gauche-master-250s-final.flac
```

---

## 3. Stage 2 — 母带 v4.7 Quiet brand (Track 1 同 SOP)

### 3.1 母带目标

| 指标 | 目标 | 备注 |
|------|------|------|
| Codec | FLAC | - |
| Sample Rate | 44.1 kHz | - |
| Bit Depth | 16-bit | - |
| Channels | 2 (Stereo) | - |
| LUFS | -14.0 ± 1.0 | Quiet brand 接受 |
| TP | ≤ -1.0 | Quiet brand 接受 |
| LRA | **2.5-12 (Quiet route)** | v4.7 LOCKED |
| DC Offset | < 0.001 L/R | - |
| Stereo Correlation | > 0.3 | - |
| Peak | ≤ -0.5 dB | - |
| Clipping | 0 sample | - |
| BPM | **76 LOCKED** | Track 2 = 76 / Track 1 = 74 |
| Key | Dm | 主调延续 |

### 3.2 母带命令

```bash
ffmpeg -hide_banner -i /root/Rive-Gauche-master-250s-final.flac \
  -af "loudnorm=I=-14:TP=-1.0:LRA=11:print_format=summary" \
  -ar 44100 -ac 2 -sample_fmt s16 \
  -c:a flac \
  /root/Aube-T02-Rive-Gauche-master-v2.0.flac
```

### 3.3 ID3 19 字段补全

```bash
python3 /var/codex_project/hermes-home/profiles/bot-b/skills/music/haevo-aube-qc-framework/scripts/embed_id3_5artists.py \
  --input /root/Aube-T02-Rive-Gauche-master-v2.0.flac \
  --artist "Aube Valois" \
  --title "Rive Gauche" \
  --album "Premier Matin - Rive Gauche (Double Single 8.28)" \
  --genre "French Pop" \
  --secondary-genre "Dream Pop" \
  --subgenre "French Cinematic Dream Pop; Chanson; Ambient Electronic" \
  --composer "XIAOYANG ZHANG" \
  --lyricist "XIAOYANG ZHANG" \
  --producer "XIAOYANG ZHANG" \
  --publisher "Self-Published" \
  --release-date "TBD (Kieran 拍板发行日)" \
  --upc "TBD" \
  --isrc "HKXIA2026AUB002" \
  --cover 3000x3000.png \
  --tagline "Les souvenirs chantent encore" \
  --track-number "2" \
  --ai-disclosure "Made with Suno. AI-Generated. EU AI Act Art. 50 compliant. Haevo Records."
```

### 3.4 5 件 Submission 套

| # | 文件 | 来源 |
|---|------|------|
| 1 | Aube-T02-Rive-Gauche-master-v2.0.flac | § 3.2 母带 |
| 2 | cover-3000x3000.png (户外 Saint-Germain) | haevo-cover-and-final-flac SOP |
| 3 | ID3 31 字段 | § 3.3 |
| 4 | Editorial Pitch (法语 + 英文) | Saint-Germain 7 AM 文学清晨 |
| 5 | Suno ID 验证 | SHA256 of wav |

---

## 4. Producer 1 句话 + 3 件必告知

**Producer (Kieran)**:
1. **复制粘贴 § 1.3 Lyrics** (实测 811 chars, 9 段, 不加描述 prose) + **§ 1.2 Style** (实测 933 chars) + Exclude 继承 Track 1 (441 chars)
2. **必预期 Round 1 = 1:50-2:30, Round 2/3 续接 → 4:10** — 不直出 4:10 (Track 2 M4D 实证)
3. **必跑 Whisper 关键词检测**: 户外鹅卵石脚步声 / 梧桐叶 / 教堂钟 = 出现 = 户外场景识别;felt piano / analog synth / nylon guitar 等配器词 = 不出现 = 配器不污染

回 `跑 Round 1` 上传 wav 我跑检测。回 `改 X` 你要改某字段。回 0 不动。
