# Rive Gauche Track 2 Round 1 — 5 维度评分实测报告

**下载日期**: 2026-07-13
**Sound DNA v2.0 + SOP v2.0 LOCKED** Producer 跑出
**3 候选 A1/A2/A3 实测** — 待 Kieran 听感 1 句话

---

## 5 维度实测 LOCKED

| 维度 | A1 | A2 | A3 | LOCKED 标准 |
|------|----|----|----|-------------|
| **时长** | **3:43.32** (223.32s) | **3:40.00** (220.00s) | **3:29.96** (209.96s) | 250s 目标 / 3:20-4:30 区间 |
| 采样率 | 48 kHz | 48 kHz | 48 kHz | 44.1 kHz LOCKED (待 downsample) |
| 声道 | 2 (Stereo) | 2 (Stereo) | 2 (Stereo) | 2 LOCKED |
| **LUFS 实测** | -12.9 ⚠ | -13.0 | -13.0 | -14 ± 1 Spotify / Quiet brand ±2 |
| TP | -1.0 ✓ | -1.0 ✓ | -1.0 ✓ | ≤ -1.0 LOCKED |
| **LRA** | 5.2 ✓ | 4.3 ✓ | 4.7 ✓ | 2.5-12 (Quiet route v4.7) |
| **vocal hit rate** (Whisper) | **42%** | **32%** | **37%** | 32%+ 全 PASS (Suno 法语辨识度限制)|
| **Leak 检测** (Pitfall #19) | **0/13 ✓** | **0/13 ✓** | **0/13 ✓** | 0 LOCKED |
| **Pass 复读** (overlap) | 0.00 ✓ | 0.08 ✓ | 0.00 ✓ | ≤ 0.5 LOCKED |
| Top gap | 25s | 16s | 23s | < 30s LOCKED |
| md5 | d3248b97... | 1a4e8ef6... | 68cb90a4... | - |

---

## 6 件关键发现 LOCKED

1. **A1 LUFS = -12.9 ⚠** = 距 -14 target +1.1 dB (Quiet brand ±1 边界勉强,A2/A3 -13.0 = -1 dB 比较 OK)
2. **3 段 Pitfall #18/19 修复成功** (Leak count = 0, Producer 必删描述 prose 工作有效)
3. **3 段均无 Pass 1/2 复读** (overlap 0.00-0.08, 远低于 0.5 阈值)
4. **Whisper vocal % 估量偏大** (multilingual tiny 翻译 ghost word, **Kieran 听感优先 LOCKED**)
5. **3 段时长都短于 Sound DNA v2.0 LOCKED 250s** — 需要 Round 2/3 Continue 续到 4:10
   - A3 时长最短 3:30,Round 2 续接空间最大 (50s 留)
   - A1 时长最长 3:43,Round 2 续接空间 27s 留
6. **3 段 Top gap 都在 16-25s** — 都是 breakable arrangement, 不算 fill 段 < 10s 不自然

---

## LUFS 距 LOCKED -14 目标差距 (诚实告知)

- A1 = -12.9 → 距 -14 +1.1 dB (Quiet brand 接受)
- A2 = -13.0 → 距 -14 +1.0 dB (Quiet brand 接受)
- A3 = -13.0 → 距 -14 +1.0 dB (Quiet brand 接受)

**全部接受, 但** SPOTIFY 默认推荐 -14 LUFS, 1-pass loudnorm 拉到 -14 1 dB 即可。

---

## Kieran 听感请求 (Pitfall #14 LOCKED)

听感决定 bot-b Best/Second/Reject 决策。3 段都无 Leak + 无复读:

1. **A1** (3:43, hit rate 42%, top gap 25s) — 听整体法语识别度 + Track 1 vs Track 2 主调延续感 (A1 hit rate 最高 = 法语发音最清晰)
2. **A2** (3:40, hit rate 32%, top gap 16s) — 听整体"户外鹅卵石脚步声"有没有出现 (Track 2 主识别音 LOCKED)
3. **A3** (3:30, hit rate 37%, top gap 23s, 时长最短) — 听 250s 续接到 4:10 的空间是不是最佳 (Round 2 最易续)

---

## bot-b evaluation-only LOCKED (Pitfall #19)

- ✅ 5 项必跑实测数据 (ffprobe/loudnorm/Whisper/Pitfall #19/Pass 复读) = 全完成
- ❌ 不推 Best/Second/Reject (Kieran 听感 > bot-b 自动评分, LOCKED)
- ❌ 不推 Round 2/3 续接方案 (待 Kieran 决定)

---

## 待 Kieran 输入

回 `听 A1` / `听 A2` / `听 A3` / `全听` 整理 5-维度评分决策表。
回 `改 X` 你要改某字段。
回 0 不动。
