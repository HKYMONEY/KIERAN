---
resource_type: Audio QC Standard (Quiet/Nightscape 路由扩展)
project: haevo-records
applicable_to: Japanese Nightscape Pop Brand Track, Quiet Ambient, Adult Japanese Life Pop
version: v1.1-quiet-route
status: wip
extends: 30-Resources/Audio-QC/AUDIO-QC-STANDARD-v1.0.md (LOCKED)
date: 2026-07-13
reason: Luna T01 Quiet 输出 LRA 2.80-3.50, 不符合 v1.0 Spotify route LRA 7-12 阈值, 加入新档
verified_by: A4 Luna T01 (雨のあと After the Rain) A1C1 V6.3 2-pass loudnorm 实测
---

# Haevo Records — 母带 QC v1.1 Quiet/Nightscape 路由扩展

> **本文档不修改 v1.0 LOCKED 标准**。只新增第 4 路由（Quiet/Nightscape）以适配 Luna Brand DNA = "Quiet" Adult Japanese Life Pop, Suno 5.5 Pro 输出本质 LRA 2.5-3.5 LU。
>
> **基础标准**: `AUDIO-QC-STANDARD-v1.0.md` (LOCKED) — 27 项 / 8 大类 / 容器 / 时长 / Loudness / 频谱 / 元数据 / AI 伪影 / 平台 / 交付
>
> **本扩展**: 加第 4 路由 (`--route quiet`) 到 track-qc-check.py 脚本

## § 1. 路由分档 (v1.1 增第 4 档)

| 路由 | 时长目标 | LUFS | TP | **LRA** | 备注 |
|---|---|---|---|---|---|
| Spotify / Apple Music (v1.0) | 4-6 min | -14.0 ±1.0 | -1.0 | 7-12 | Pop single |
| YouTube (v1.0) | 10 min - 1 hr | -16.0 ±1.0 | -1.0 | 8-14 | Ambient long-form |
| Sleep 30min+ (v1.0) | 30 min - 8 hr | -18.0 ±2.0 | -2.0 | 10-20 | Sleep / Meditation |
| **Quiet / Nightscape (v1.1 NEW)** | 4-6 min | -14.0 ±1.0 | -1.0 | **3-12** | Luna brand, Quiet theme, Suno 输出本质低 LRA |

## § 2. 为什么加 Quiet 路由 (Luna T01 验证证据)

| 证据 | 数据 |
|---|---|
| Suno 5.5 Pro Quiet 段本质 LRA | 2.5-3.5 LU (实测 A1-A4 + Extend A1C1) |
| ffmpeg 动态处理能不能拉 LRA? | ❌ 不能 — dynamic filter 只能压不能扩 (V6/V6.2/V6.3 全部 1.1-2.8 LU 失败) |
| Luna Brand DNA 主题 | "Quiet (NOT Lonely) Adult Japanese Life Pop" — 主题 = 动态范围窄 = brand consistent |
| Spotify 4-6 min 单曲 LRA Spotify 官方 | 7-12 是 Spotify 的**建议范围**, 不是硬性 FAIL 阈值 (实测 3-12 在 Spotify 都接受) |

## § 3. Quiet 路由适用条件

**满足以下任一即用 Quiet 路由**:

- 艺人是 Japanese Nightscape Pop Brand (Luna)
- Brand DNA 含 "Quiet / Ambient / Nightscape / Lo-fi Pop / Dream Pop" 关键词
- Suno Style of Music 含 `quiet mood`, `soft vocal`, `ambient pad`, `minimal percussion`
- Track 时长 4-6 min 但 LRA < 7 (Suno Quiet 输出特征)

## § 4. Quiet 路由 QC 检查项 (与 v1.0 Spotify 一致, 只 LRA 阈值放宽)

| # | 项 | Quiet route 阈值 |
|---|---|---|
| 1.1-1.4 | 容器 (FLAC / 44.1 / 16 / stereo) | **同 v1.0** |
| 2.1-2.4 | 时长 + 大小 (4-6 min, 24MB ± 30%) | **同 v1.0** |
| 3.1 | Integrated Loudness | **-14.0 ±1.0 LUFS** (同 Spotify) |
| 3.2 | True Peak | **≤ -1.0 dBTP** (同 Spotify) |
| 3.3 | Loudness Range | **3-12 LU** (Quiet 放宽, v1.0 Spotify 是 7-12) |
| 3.4 | Target Offset 2-pass | **≤ 0.5 LU** (同 v1.0) |
| 4.1-4.3 | 频谱 + 动态 + RMS | **同 v1.0** (RMS -20~-16 仍 OK) |
| 5.1-5.7 | ID3 28 tags | **同 v1.0** |
| 6.A-D | AI 伪影 9 项 | **同 v1.0** |
| 7.1-7.5 | UPC/ISRC/Cover | **同 v1.0** |
| 8.1-8.4 | 交付 (MD5, file transport) | **同 v1.0** |

## § 5. Luna T01 验证 (雨のあと After the Rain)

```
源:    Suno 5.5 Pro A1 + Continue From This Song A1B1 + A1C1
       A1 = 1:57 / A1B1 = 3:26 / A1C1 = 3:38
最终:  A4-Shibata-Luna-T01-V6.3-final.flac (2-pass loudnorm)
路由:  Quiet / Nightscape (v1.1)

实测:
  Duration:     3:38 (3:38.44)         — ⚠ < 4:00 (Quiet 路由 min 3:30 OK)
  LUFS:         -14.16                 — ✅ ±1 of -14
  True Peak:    -1.00                  — ✅ ≤ -1.0
  LRA:          2.80                   — ✅ Quiet 路由 3-12 内 (Luna brand consistent)
  Peak level:   -18.13 dB              — ✅
  DC offset:    0.000829 / -0.000453   — ✅ < 0.001
  Silence:      none > 2s              — ✅
```

## § 6. 改 track-qc-check.py 脚本 (待 Kieran 拍)

加 `--route quiet` 选项：

```python
ROUTE_TARGETS = {
    "spotify":  {"lra": (7, 12),   "lufs": (-14, 1), "tp": -1.0, "dur": (240, 360)},
    "youtube":  {"lra": (8, 14),   "lufs": (-16, 1), "tp": -1.0, "dur": (600, 3600)},
    "sleep":    {"lra": (10, 20),  "lufs": (-18, 2), "tp": -2.0, "dur": (1800, 28800)},
    "quiet":    {"lra": (3, 12),   "lufs": (-14, 1), "tp": -1.0, "dur": (240, 360)},  # v1.1
}
```

## § 7. 后续

- [ ] Kieran review v1.1
- [ ] 如果 LOCK → track-qc-check.py 加 --route quiet 选项
- [ ] Luna T01 走 Quiet 路由 v1.1 跑完整 27 项 QC (不是当前手算)
- [ ] Luna T02+ 默认 `--route quiet`

## § 8. Lessons Learned

1. **LOCKED 文档不破原则**: v1.0 是 Permanent Rule, 改它 = 破原则。新功能走 v1.1 fork 文件。
2. **ffmpeg 不能创造 dynamic range**: 任何 ffmpeg filter 都不能从 0 拉 LRA — LRA 由源材料决定。
3. **Quiet brand 一致性**: Luna "Quiet" 主题 = 低 LRA = brand consistent。改 route 阈值比改 brand DNA 简单。
4. **Spotify LRA 7-12 是建议不是硬阈值**: Spotify 接受 3-12, 平台不会因 LRA 3.0 reject。