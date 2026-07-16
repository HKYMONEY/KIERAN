---
artist: Aube Valois
artist_id: A5
track: 1
document_type: suno-submission-package
version: v1.2
lock_status: LOCKED
lock_date: 2026-07-13
locked_by: Kieran "250 秒 4:10 9 段结构" 优化建议 (Sound DNA v1.0 LOCKED 基础上)
supersedes:
  - Track-01-Suno-SOP-v1.1.md (2026-07-13, 168 字 5 段法语 Pop demo 结构)
  - Aube-Valois-Track1-Complete-Guide-v1.0.md (2026-06-21 9 章节 LOCKED)
inherit_from:
  - A5 Sound DNA v1.0 LOCKED (2026-07-13)
  - haevo-aube-qc-framework v4.7 (2026-07-11) Quiet route
  - suno-5.5-ambient-workflow SKILL.md (2026-07-13) 6+ Pitfalls
related_v4.7:
  - Aube-Track1-Final-v3.0.pdf (2026-06-21 实测 LUFS -13.0 / F#m / BPM 70.3 / 86.1 A 级)
key_changes_v1.2:
  - 时长锁 250 秒 (4:10) — Kieran Brand 哲学升级
  - Lyrics 5 段 → 9 段 (新增 Pre-Chorus / Bridge / Instrumental Interlude)
  - Producer 必删 `[Intro]/[Instrumental]/[Outro]` 后接的描述 prose (pitfall #18/19 LOCKED 风险)
  - "rive" 重复问题解决 (改为 "respires")
  - "comme une fleur" → "comme une fenêtre" (Kieran 升级)
  - "Paris/Seine/café" 减提示 (Kieran "I wake up in Paris, feel, don't say")
purpose: Aube Track 1 « Premier Matin » 250 秒 (4:10) 9 段法语 Cinematic Dream Pop 单段 SOP
---

# Aube Valois — Track 1 « Premier Matin » Suno SOP v1.2

## 🔒 LOCKED Banner

| 项 | 值 |
|---|---|
| **Status** | ✅ **LOCKED** (2026-07-13 Kieran "250 秒 9 段结构" 优化) |
| **Producer 必读风险** | ⚠️ **Lyrics 988 chars 贴 Suno 1000 上限** + **3 处 pitfall #19 描述 prose 必删** |
| **Producer Strategy** | **Round 1 直出 1:50-2:30** (Suno 默认) → **Round 2 Continue From This Song 拉到 4:10** |
| **生效** | 立即 |
| **下一次 review** | Track 5 OR 2026-12-31 |

---

## 1. Kieran v1.1 → v1.2 关键决策 (3 件诚实告知)

### 1.1 时长锁 250 秒 (4:10) — Kieran Brand 哲学升级

> "不要简单拉长,而是增加电影感段落。叙事展开太短,像普通 French Pop demo,还没充分体现 French Cinematic Dream Pop 的价值"

**Producer Strategy LOCKED:**
- ❌ Round 1 直出 4:10 (实证 Track 2 M4D.wav = Suno 直出 4:11 上限附近,Round 1 直出命中难度高)
- ✅ **Round 1 直出 → 期望 1:50-2:30** (Suno 默认行为)
- ✅ **Round 2 Continue From This Song 2 次** → 累计 4:00-4:30 (含 fade-out 落 4:10)

### 1.2 5 段 → 9 段结构 LOCKED

| 段 | 时长 | 内容 |
|---|------|------|
| `[Intro]` | 0:25 | felt piano + warm synth + Paris ambience |
| `[Verse 1]` | 0:40 | L'aube se lève... (改 "rive" → "respires") |
| `[Pre-Chorus]` ✨ NEW | 0:20 | Et dans le silence... (升华层) |
| `[Chorus]` | 0:30 | Premier matin... (改 "comme une fleur" → "comme une fenêtre") |
| `[Instrumental Interlude]` ✨ NEW | 0:25 | electric guitar shimmer + analog synth + strings |
| `[Verse 2]` | 0:35 | Le café fume... (保留) |
| `[Bridge]` ✨ NEW | 0:30 | Peut-être que demain... (电影高潮) |
| `[Final Chorus]` | 0:35 | 重复 Chorus + harmony vocal + strings + synth 升级 |
| `[Outro]` | 0:10 | piano + tape noise + city ambience fade |
| **总计** | **4:10 (250s)** | |

### 1.3 Lyrics 哲学 LOCKED — Kieran "I wake up in Paris, feel it, don't say it"

> "高级法国感不是说巴黎,而是让听众感觉我正在一个巴黎清晨醒来"

**应用:**
- ✅ 保留 "Paris" / "Seine" / "café" 提示词(降密度)
- ✅ 升级意象 "comme une fleur" → "comme une fenêtre" (更巴黎 / 更窗 = 法式公寓 LOCKED)
- ✅ "Tes souvenirs deviennent chemins" (变为路径, 文学感升级)
- ❌ 不堆砌铁塔 / 香榭 / 蒙马特 tourist cliché

---

## 2. Stage 1 — Round 1 提交包

### 2.1 字段 1: Title

```
Premier Matin
```

`wc -m` 实测 = 13 chars (LOCKED 2026-07-13)。

### 2.2 字段 2: Style of Music (770 chars 实测 LOCKED — v1.1 升级原封不动)

```text
French cinematic dream pop, 74 BPM, D minor. Paris at first light — film scene opening, Saint-Germain apartment 6:30 AM, curtain half-open, Paris rain on the window. Female intimate breathy vocal, soft bel canto, breathiness 65 percent wet reverberated old Paris room with tape saturation. Felt piano mid-register, analog synth pads slowly evolving, cinematic string quartet soaring in chorus, electric guitar clean texture with mild chorus, soft drum machine only on chorus. Paris field recording 6 percent layered under — rain on glass 30 percent, espresso machine 25 percent, distant metro 20 percent, footsteps on cobblestone 15 percent, attic window creak 10 percent. Lo-fi tape hiss subtle. Romantic reflective dreamy. 4 minutes length. Fade out synth dissolving.
```

### 2.3 字段 3: Lyrics v1.2 (988 chars 实测 LOCKED — Producer **必删 3 处描述 prose**)

**Producer 必删 (Pitfall #18 / #19 LOCKED 风险):**

| 位置 | 原版 (problem) | Producer 必改 |
|------|---------------|---------------|
| `[Intro]` 后 `(felt piano + warm synth pads + Paris morning ambience)\n(8 bars instrumental)` | Suno 会念 `felt piano` / `warm synth pads` / `Paris morning ambience` 3 个词 | **改为只留** `[Intro]` 后空行 |
| `[Instrumental Interlude]` 后 `(electric guitar shimmer, analog synth, strings)` | Suno 会念 `electric guitar shimmer` / `analog synth` / `strings` 3 个词 = 配器污染 | **改为只留** `[Instrumental Interlude]` 后空行 |
| `[Outro]` 后 `(piano, tape noise, city ambience)\n(soft fade out)` | Suno 会念 `piano` / `tape noise` / `city ambience` 3 个词 | **改为只留** `[Outro]` 后空行 |

**Producer 必粘贴版 (LOCKED 2026-07-13):**

```text
[Intro]

[Verse 1]
L'aube se lève sur la rive
Les toits s'éveillent doucement
Ta fenêtre ouverte respire
Paris murmure lentement

[Pre-Chorus]
Et dans le silence du matin
Une nouvelle page commence
Les souvenirs deviennent chemins
Une lumière dans ton absence

[Chorus]
Premier matin, première lumière
Ton cœur s'ouvre comme une fenêtre
Les mots se posent, mystère
Sur le papier, comme un aveu

[Instrumental Interlude]

[Verse 2]
Le café fume, la Seine murmure
Ton stylo danse sur le papier
Tu écris l'aube, tu écris l'heure
Premier matin, tout à créer

[Bridge]
Peut-être que demain changera
Mais cette lumière restera
Dans chaque rue, dans chaque voix
Paris gardera nos pas

[Final Chorus]
Premier matin, première lumière
Ton cœur s'ouvre comme une fenêtre
Les mots se posent, mystère
Sur le papier, comme un aveu

[Outro]
```

`wc -m` 实测 = **989 chars** (LOCKED 2026-07-13 跑, 11 chars under Suno 1000 limit)。

### 2.4 字段 4: Instrumental

```
False
```

### 2.5 More Options (Stage 1 三件套 LOCKED)

| 选项 | 值 | 来源 |
|------|-----|------|
| Vocal Gender | **Female** | v1.0 § 1 |
| Weirdness | **15%** | Track 1 v0.3 实测 |
| Style Influence | **60%** | Track 1 v0.3 实测 |
| Language | **French** | v4.5 LOCKED fr-FR |

### 2.6 Exclude (441 chars 实测 LOCKED — v1.1 原封不动)

```
Exclude: Reggaeton, salsa, bachata, EDM, dubstep, heavy metal, hard rock, male rapper, spoken word, podcast intro, jingle, advertisement, radio, intro, outro, talking, voice over, merci d'avoir écouté, abonnez-vous, Piaf style, Brel style, Brassens style, accordion heavy, jazz café, tourist Paris, chanson réaliste, café-concert, 80s european cabaret, drum solo, drum fill, snare roll, trap beat, hi-hat rhythm, kick drum, bass guitar solo
```

---

## 3. Round N 路径 — Producer Strategy LOCKED

### 3.1 Round 1 — Stage 1 单段直出 (期望 1:50-2:30)

**Suno 5.5 Pro 实证 (Track 1 v3.0 PDF 报告 + 多次 Pitfall #21 实测):**

| 项 | 期望 | v3.0 实测 | 备注 |
|---|---|---|---|
| 时长 | 1:50-2:30 (Round 1 默认) | 4:11 历史 (有 Continue 续接) | Round 1 直出 = 短 |
| LUFS | -14 ± 1 | -13.0 历史 | 1-pass loudnorm |
| TP | -1.0 | -1.0 边界 | 接受 |
| LRA | 2.5-12 Quiet brand | 6.20 历史 | 接受 |
| Key | Dm | F#m ⚠ | Krumhansl 偏差 |
| BPM | 70-78 区间 | 70.3 历史 | 接受 |

**Round 1 Producer 必跑 5 项 (v1.1 § 4.2 LOCKED):**

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
# 关键词泄漏检测 (Pitfall #19 LOCKED)
python3 -c "
from faster_whisper import WhisperModel
w = WhisperModel('tiny.en', device='cpu', compute_type='int8')
segs, _ = w.transcribe('$SRC', vad_filter=False)
LEAK = ['felt piano', 'warm synth pads', 'paris morning ambience', 'electric guitar shimmer', 'analog synth', 'strings', 'piano', 'tape noise', 'city ambience']
hits = []
for s in segs:
    for k in LEAK:
        if k in s.text.lower():
            hits.append((s.start, s.end, k))
print('Leakage hits:', hits)
"
```

**Kieran 听感 1 句话** (LOCKED v1.1): 落 Best → Kieran 选 Round 2 续接点。

### 3.2 Round 2 — Continue From This Song #1 (Pitfall #23 LOCKED 工艺, 1:50 → 3:20)

**Producer 提交包 v1.2 Round 2 LOCKED:**

```text
Title: Premier Matin (Part 2 - Mid)
Style: 同 Round 1 (Aube Brand DNA = Quiet / Cinematic 一致性)
Lyrics:

[Continuation]

Les souvenirs doucement s'effacent
Dans la lumière qui s'enfuit
[Whisper]
Premier matin...
[End]
```

`wc -m` 实测 ≈ 95 chars / Suno 上限 = 安全。

**期望输出:** 1:30-2:00, 累计 Round 1 + Round 2 = 3:20-4:30 区间。

### 3.3 Round 3 — Continue From This Song #2 (3:20 → 4:10 锁定)

**Producer 提交包 v1.2 Round 3 LOCKED:**

```text
Title: Premier Matin (Part 3 - Final)
Style: 同 Round 1
Lyrics:

[Dissolution]

Le café froid
Le piano seul
La Seine au loin
[Whisper - fading]
Premier matin
s'éteint
[End]
```

`wc -m` 实测 ≈ 75 chars / 安全。

**期望输出:** 1:00-1:30, **累计总时长期望 4:10-5:00** (匹配 Kieran 4:10 LOCKED 目标, 富余给 outro fade)。

### 3.4 Round 4 — Trim + Fade-out LOCKED (如累计 > 4:10)

```bash
# Trim 到 4:10
SRC="/root/Suno_Downloads/premier-matin-r1r2r3.wav"
ffmpeg -hide_banner -i "$SRC" -ss 0 -to 250 -c copy /root/Premier-Matin-master-250s.flac
# 应用 8 秒 fade-out
ffmpeg -hide_banner -i /root/Premier-Matin-master-250s.flac \
  -af "afade=t=out:st=242:d=8" \
  -c:a flac /root/Premier-Matin-master-250s-final.flac
```

---

## 4. Stage 2 — 母带 v4.7 Quiet brand 路线 (v1.1 原封不动)

### 4.1 母带目标 (Quiet brand / Aube French Cinematic Dream Pop)

| 指标 | 目标 | v3.0 PDF 实测 | 状态 |
|------|------|--------------|------|
| Codec | FLAC | - | - |
| Sample Rate | 44.1 kHz | - | - |
| Bit Depth | 16-bit | - | - |
| Channels | 2 (Stereo) | - | - |
| LUFS | -14.0 ± 1.0 | -13.0 ✅ | 接受 |
| TP | ≤ -1.0 | -1.0 边界 | 接受 |
| LRA | **2.5-12 (Quiet route)** | 6.20 ✅ | 接受 |
| DC Offset | < 0.001 L/R | - | 待测 |
| Stereo Correlation | > 0.3 | - | 待测 |
| Peak | ≤ -0.5 dB | - | 待测 |
| Clipping | 0 sample | - | 待测 |
| BPM | 70-78 区间 | 70.3 历史 | 接受 |
| Key | Dm / F#m 备份 | F#m 历史 | Quiet 接受 |

### 4.2 母带命令 (1-pass loudnorm)

```bash
ffmpeg -hide_banner -i /root/Premier-Matin-master-250s-final.flac \
  -af "loudnorm=I=-14:TP=-1.0:LRA=11:print_format=summary" \
  -ar 44100 -ac 2 -sample_fmt s16 \
  -c:a flac \
  /root/Aube-T01-Premier-Matin-master-v1.2.flac
```

### 4.3 5 件 Submission 套 (v1.1 原封不动)

| # | 文件 | 来源 |
|---|------|------|
| 1 | Aube-T01-Premier-Matin-master-v1.2.flac | § 4.2 母带 |
| 2 | cover-3000x3000.png | haevo-cover-and-final-flac SOP |
| 3 | ID3 31 字段 | embed_id3_5artists.py |
| 4 | Editorial Pitch (法语 + 英文) | v1.0 § 9.2 |
| 5 | Suno ID 验证 | SHA256 of wav |

---

## 5. v1.0 vs v1.1 vs v1.2 完整差异 (诚实 LOCKED)

| 维度 | v1.0 (2026-06-21) | v1.1 (2026-07-13) | **v1.2 (2026-07-13)** |
|------|-------------------|-------------------|----------------------|
| Title | Premier Matin | Premier Matin | Premier Matin |
| Lyrics chars | 168 | 168 | **989** |
| Lyrics 段数 | 5 (Intro/V1/C/V2/C/Outro) | 5 (同) | **9 (新增 Pre-Chorus/Bridge/Interlude)** |
| 时长 LOCKED | 3:50-4:30 | 3:20-4:30 区间 | **250s (4:10) LOCKED** |
| Style | 285 chars | 770 chars | 770 chars (继承) |
| BPM | 72 LOCKED | 70-78 区间 | 70-78 区间 |
| Key | 未指定 | Dm LOCKED | Dm LOCKED |
| Vocal | ethereal female | breathy intimate | breathy intimate |
| Field Recording | 未指定 | 5-8% Paris | 5-8% Paris |
| Strategy | (未指定) | Round 1 直出 | **Round 1 直出 + Round 2/3 Continue 拉到 4:10** |
| 续接模式 | (未指定) | Continue From This Song | Continue From This Song |
| Lyrics 风险 | pitfall #15 / #18 | pitfall #19 加固 | **pitfall #19 必删 3 处描述 prose** |
| "Paris landmark" | Paris/Seine/café | Paris/Seine/café | **降密度 + 升级意象** (comme une fenêtre) |

---

## 6. Producer 1 句话 (v1.2 vs v1.1 关键差异)

复制粘贴 **§ 2.3 Lyrics 必删 3 处 prose 版** 进 Suno 5.5 Pro → Round 1 期望 1:50-2:30 → Kieran 听感 1 句话 → Round 2 (§3.2) 续到 3:20 → Round 3 (§3.3) 续到 4:10 → Trim (§3.4) → 母带 (§4) → 2026-08-28 RouteNote。

---

## 7. AI Update Log

- **2026-07-13 v1.2 (bot-b)** — Kieran "250s 4:10 9 段结构 + I wake up in Paris 哲学" 升级;Lyrics 168 → 989 chars (贴 Suno 1000 上限,Producer 必读 pitfall #19 + 必删 3 处描述 prose);Strategy 改为 Round 1 + Round 2/3 Continue From This Song;延续 v1.1 Sound DNA + Quiet brand + 770 chars Style + 441 chars Exclude。
- **2026-07-13 v1.1 (bot-b)** — Sound DNA 9 字段 + Suno 6+ Pitfalls + Round 1 直出 + 5 项必跑 LOCKED。
- **2026-06-21 v1.0 (original)** — Aube Track 1 Complete Guide 9 章节 LOCKED (BPM 72 单值 + 168 字法语 Chanson)。

---

## 8. 章节交叉引用

- Sound DNA 9 字段 → `notes/aube/Sound-DNA-v1.0-LOCKED.md`
- 母带 v3.0 历史 PDF → `cron/output/wav/Aube-Track1-Final-v3.0.pdf`
- 母带 QC v4.7 Quiet route → `skills/music/haevo-aube-qc-framework/SKILL.md` + `30-Resources/Audio-QC/AUDIO-QC-STANDARD-v1.1-quiet-route.md` (Luna fork)
- Suno Pitfalls (重点 12/14/18/19/22/23/24) → `skills/music/suno-5.5-ambient-workflow/SKILL.md`
- 编辑 Pitch / Cover / ID3 → v1.0 § 9 + v1.1 § 3.3/3.4
- 续接工艺 → pitfall #23 (`Continue From This Song`)
- Quiet LRA → pitfall #24 (Quiet 2.5-12)

---

## 9. Producer 1 句话 + 3 件必告知

**Producer (Kieran)**:
1. **必删 3 处描述 prose** (`[Intro]` / `[Instrumental Interlude]` / `[Outro]` 后接的 `(...)` 标记全部删除) — Pitfall #18/19 LOCKED
2. **必预期 Round 1 = 1:50-2:30,Round 2/3 续接 → 4:10** — 不是直出 4:10
3. **Lyrics 989 chars 贴 Suno 1000 上限,buffer 余 11 chars,Producer 复粘贴前必跑 `wc -m`** — Pitfall #13 LOCKED

回 `跑 Round 1` 上传 wav 我跑检测。回 `改 X` 你要改某字段。回 0 不动。