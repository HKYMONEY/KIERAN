# A4 Luna T01 — Suno Extend Continuation Prompt

## 前提

A1 当前 1:57 (117.72s)，目标 4:00 (240s)。
A1 Best QC score 64.7%，复读 0。
**需要在 Suno 网页/App 操作**，WSL 端无法执行 Extend。

---

## 操作步骤

1. 打开 https://suno.com → 找到 A1 wav
2. 点 A1 → "Continue From This Song" / "Extend"
3. Continue at: **1:50**（留 7s 缓冲给拼接 seam）
4. 在新 Lyrics 框里**粘贴下面 Continuation Prompt A**（从 1:50 → 4:00）
5. Style of Music 沿用 v0.1 Suno Prompt 已写（不要改）
6. Click Extend → 等生成（30s-60s）
7. 重复 1-3 次直到总长度 ≥ 4:00

---

## Continuation Prompt A（from 1:50 → 4:00）

```
[Instrumental - 40 seconds, rain continues, soft piano solo]

[Whisper]
午前4時
東京の窓
青く光る信号

[Soft Vocal]
誰も急がない
ただ歩く
ただ帰る

[Instrumental - 35 seconds, piano + analog synth pad]

[Whisper]
雨のあと
コンビニの灯り

[Soft Vocal - fading]
東京の夜
静かに好き

[Outro - Instrumental - 30 seconds]
rain fade
train window ambience
faint city lights

[Whisper - dissolving]
また明日
東京の夜
```

**预计输出**：从 1:50 接续到约 3:00-3:20。**第一次 Extend 大概率不会直接到 4:00**，需要第二次 Extend。

---

## 第二次 Extend（如果第一次到 3:00-3:20）

Continue at: **2:50-3:00**（看第一次 Extend 实际结束位置）

```
[Instrumental - 30 seconds, very sparse, just rain ambience]

[Whisper - very soft]
また明日

[Instrumental - 25 seconds, fade to silence]

[End]
```

**总长度目标**：3:30-4:00。**Extend 2 次基本保证 4:00**。

---

## Extend 完后的 Stage 2 Loudnorm（WSL 端执行）

Extend 完，下载拼接后的 wav 到 `/tmp/luna-a1a4/` 命名为 `A1-extended-4min.wav`，然后跑：

```bash
cd /tmp/luna-a1a4

# Stage 2: 1-pass normalize 到 -14 LUFS, TP=-1.0, LRA=11
ffmpeg -hide_banner -nostats -i "A1-extended-4min.wav" \
  -af loudnorm=I=-14:TP=-1.0:LRA=11 \
  -ar 44100 -ac 2 -c:a flac \
  A4-Shibata-Luna-T01-after-rain-A1-extended-mastered.flac

# Verify LUFS
ffmpeg -hide_banner -nostats -i "A4-Shibata-Luna-T01-after-rain-A1-extended-mastered.flac" \
  -af loudnorm=I=-14:TP=-1.0:LRA=11:print_format=json -f null - 2>&1 | tail -10
```

**Stage 2 输出应符合 v4.7 Spotify route**:
- LUFS: -14.0 ±0.5
- TP: ≤ -1.0
- LRA: 7-12（Stage 2 升到 9-11 范围）

---

## Extend 完 + Stage 2 后，跑 5 项 quick verify

```bash
# 1. duration
ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 \
  A4-Shibata-Luna-T01-after-rain-A1-extended-mastered.flac

# 2. peak / clipping
ffmpeg -hide_banner -nostats -i "A4-Shibata-Luna-T01-after-rain-A1-extended-mastered.flac" \
  -af "astats=metadata=1:reset=1" -f null - 2>&1 | grep -E "(Peak level|Number of samples)"

# 3. silence detect (no > 2s silence in middle)
ffmpeg -hide_banner -nostats -i "A4-Shibata-Luna-T01-after-rain-A1-extended-mastered.flac" \
  -af silencedetect=noise=-30dB:d=2 -f null - 2>&1 | grep silencedetect

# 4. DC offset
ffmpeg -hide_banner -nostats -i "A4-Shibata-Luna-T01-after-rain-A1-extended-mastered.flac" \
  -af "astats=metadata=1:reset=1" -f null - 2>&1 | grep "DC offset"
```

---

## 下一步

```
X1: Extend done → 跑 Stage 2 loudnorm + 4 项 verify
X2: Extend 失败 → A2 重跑（也 64.7% 区间，lyric 略多）
X3: Extend 失败 → A 增 lyrics 重生
X4: STOP
```

回 1 句我做。回 0 行不动。