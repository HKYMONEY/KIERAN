---
status: research
topic: suno-capability-test
artist: weini
purpose: Track 2 前置 gate - 验证 Suno 5.5 Pro 中文能力
created: 2026-07-11
updated: 2026-07-11
related:
  - 微霓规划书 (Track 2 IP 战略)
  - multi-artist-label-playbook SKILL.md (v4.7)
  - haevo-a-r-control-table SKILL.md
---

# 微霓 Suno 5.5 Pro 中文能力测试 v0.1

**目的**: 锁定 Suno 5.5 Pro 是否能稳定生成符合微霓 IP 的中文 Ambient/Dream Pop 作品。
**位置**: Track 2 SOP 的**前置 gate** — 不通过不发车。
**版本**: v0.1 (5 项测试, 每项 4 段跑作 + Pass/Fail 标准)

---

## 0. 测试前置条件

| 项目 | 锁定值 |
|---|---|
| Suno 版本 | 5.5 Pro (付费用户, 不更换) |
| 测试批次 | 每项 4 段 (按 haevo-a-r-control-table pitfall 7: 直接跑 4 段, 不做 2 段验证) |
| 评估工具 | Whisper tiny.en / small (zh model) + ffmpeg loudnorm + librosa chroma_cqt |
| Pass 标准 | 每项 5/5 (即 4 段里至少 3 段 Pass, ≥ 75%) |
| 总判定 | 5/5 项全 Pass → Track 2 SOP 锁定; 任何 1 项 Fail → Negative Prompt 修补 + 复跑 |

---

## 1. 测试项 1: 中文 vocal 发音准确度

### 目的
验证 Suno 5.5 Pro 中文 vocal 发音是否清晰可辨 (尤其中文声母/韵母)

### 测试方法
- 跑 4 段固定测试歌词 (8 段结构, ≥ 400 char)
- Whisper zh model transcript
- 计算字错率 (CER)

### 测试歌词 (固定 8 段模板)

```
[Intro]
(instrumental, ambient synth pad + soft piano, 8 mesures)

[Verse 1]
月色落窗台
风过无人街
远山一片青
雾起江面开

[Pre-Chorus]
留白处
思念来
夜未央
心自在

[Chorus]
千年前种下的月光
落在今夜的肩膀
不必问归向何方
安静就是远方

[Verse 2]
灯笼照空巷
雁过衡山岗
炊烟一缕香
流水向东方

[Pre-Chorus]
留白处
思念来
夜未央
心自在

[Chorus]
千年前种下的月光
落在今夜的肩膀
不必问归向何方
安静就是远方

[Bridge: voix plus intime, whisper vocal]
千年不过一瞬
月光依然相同
你我不必相逢
各自安静如风

[Instrumental Break: ambient synth solo, sustained texture]

[Chorus]
千年前种下的月光
落在今夜的肩膀
不必问归向何方
安静就是远方

[Outro: long fade out, ambient synth dissolves, 8 mesures]
```

(约 350 char, 略低于 400 char 阈值 — 测试需扩到 ≥ 400)

### Suno 参数锁定
```
Style of Music: Chinese dream pop, ambient, intimate whisper vocal, soft piano, ambient synth pad, cinematic, wide stereo, long reverb
BPM: 74
Key: D minor
Length: 4:00 (显式, 因 Style field "X minutes length" 无效)
Vocal: Female, whisper subtype
Negative Prompt: (见 §6 锁定 8 行)
Style Influence: 85%
Weirdness: 20%
```

### Pass 标准
| 指标 | Pass | Fail |
|---|---|---|
| CER (字错率) | < 15% | ≥ 15% |
| 中文声母准确 (zh/ch/sh) | ≥ 90% | < 90% |
| 中文韵母完整 (无吞字) | ≥ 85% | < 85% |
| 4 段里 Pass 段数 | ≥ 3/4 | < 3/4 |

### 评估脚本
```bash
# 1. 提取每段前 30s
for f in *.mp3; do
  ffmpeg -y -i "$f" -t 30 -af "afade=t=in:st=0:d=2" "${f%.mp3}_30s.mp3"
done

# 2. Whisper transcript
for f in *_30s.mp3; do
  whisper "$f" --language Chinese --model small --output_format txt
done

# 3. CER 计算 (vs reference lyric)
python3 cer_eval.py reference.txt output.txt
```

---

## 2. 测试项 2: 中文 lyric 结构服从度

### 目的
验证 Suno 5.5 Pro 是否服从 8 段结构 (Pre-Chorus + Bridge + Instrumental Break)

### 测试方法
- 跑 4 段同歌词 (§1 测试歌词)
- Whisper multi-window 分析 (0-5s / 0-15s / 0-30s / 0-60s / 全文)
- 检查每段是否触发对应结构

### Pass 标准
| 结构 | Pass 触发率 | Fail |
|---|---|---|
| [Intro] (instrumental pad) | 100% (4/4 段) | < 100% |
| [Verse 1] 4 行 | ≥ 75% (3/4) | < 75% |
| [Pre-Chorus] 4 行 | ≥ 75% (3/4) | < 75% |
| [Chorus] 重复段 | ≥ 75% (3/4) | < 75% |
| [Verse 2] 4 行 | ≥ 75% (3/4) | < 75% |
| [Bridge: whisper] | ≥ 75% (3/4) | < 75% |
| [Instrumental Break] | ≥ 75% (3/4) | < 75% |
| [Outro fade out] | ≥ 75% (3/4) | < 75% |

### 关键观察
- 168 char 5 段 vs 400+ char 8 段结构服从率对比 (复现 playbook suno-lyrics-400-char-threshold 实证)
- Pre-Chorus 标签是否触发新段 (vs Suno 自动合并到 Verse)
- Bridge 标签是否触发 whisper timbre 切换

---

## 3. 测试项 3: 中文意象词汇识别度

### 目的
验证 Suno 5.5 Pro 是否理解中文意象词汇 (月/雾/风/烟/山/水/灯/雁) 并在编曲/音色中体现

### 测试方法
- 跑 4 段 prompt 含 5 个意象关键词
- 评估编曲/音色是否对应

### Prompt 模板
```
Style of Music: ambient dream pop with moon imagery (soft bell synth),
fog texture (reverb wash), wind sound (subtle pad modulation),
mountain atmosphere (low drone), water texture (soft piano arpeggio),
intimate whisper female vocal, Chinese, 74 BPM, D minor, cinematic
```

### Pass 标准
| 意象 | Pass 听觉指标 | Fail |
|---|---|---|
| 月 | 含 bell / chime / soft high pad | 缺失 |
| 雾 | 长 reverb wash (≥ 3s tail) | 干声, reverb < 1.5s |
| 风 | pad modulation / breathing | 静态 pad |
| 山 | low drone (60-100Hz) | 缺失低频 |
| 水 | soft piano arpeggio / 流体感 | 缺失 |

### 评估方法
- ffmpeg 频谱分析 (检查 60-100Hz drone)
- 听感 5 维评分 (Kieran + bot-b)
- 4 段里 Pass 段数 ≥ 3/4

---

## 4. 测试项 4: 中文情感音调对位度

### 目的
验证 Suno 5.5 Pro 是否能把"思念/留白/孤独/静/梦"中文情感词翻译成对应音色

### 测试方法
- 跑 4 段, prompt 含 3 个情感关键词
- 评估音色是否对位

### Prompt 模板
```
Style of Music: ambient ballad with nostalgic longing (思念) (slow melodic phrase),
contemplative silence (留白) (sparse arrangement, long pauses),
intimate solitude (孤独) (solo whisper vocal, minimal instrumentation),
Chinese dream pop, 74 BPM, D minor
```

### Pass 标准
| 情感词 | Pass 听觉指标 | Fail |
|---|---|---|
| 思念 | melodic phrase 反复, 带 nostalgia | 无 melodic hook |
| 留白 | 段间停顿 ≥ 4s, sparse arrangement | 连续编曲无停顿 |
| 孤独 | solo vocal, minimal instrumentation | 多声部, 满编曲 |

### 评估方法
- 听感 5 维评分
- 段间停顿时长测量 (ffmpeg silencedetect)
- 4 段里 Pass 段数 ≥ 3/4

---

## 5. 测试项 5: 中文 ambient 训练集污染压制度

### 目的
验证 Suno 5.5 Pro 默认输出是否带"古筝/箫/戏腔"自动污染, 以及 Negative Prompt 8 行能否压制

### 测试方法
- 跑 2 组 (每组 4 段):
  - **组 A**: 无 Negative Prompt
  - **组 B**: 含 8 行 Negative Prompt (§6 锁定)
- Whisper + 听感对比

### Pass 标准
| 污染源 | 无 NP 污染率 | 有 NP 污染率 (目标) |
|---|---|---|
| 古筝 solo | [基线测量] | ≤ 25% (1/4) |
| 箫 solo | [基线测量] | ≤ 25% |
| 戏腔 | [基线测量] | ≤ 25% |
| 高音飙歌 | [基线测量] | ≤ 25% |
| 网络流行语 (lyric 污染) | [基线测量] | ≤ 25% |

### 评估方法
- 0-30s + 全文 Whisper transcript (检查歌词是否被替换)
- 听感检查 solo 段落
- 频谱分析检查高频尖锐成分

---

## 6. Negative Prompt 8 行锁定 (中文专项)

基于 playbook v4.7 + haevo-a-r-control-table pitfall 3 (Negative ≥ 8 行 → 89% 命中率):

```
drums, drum kit, hi-hat, snare, trap beat, EDM beat, kick drum
commercial chorus, radio structure, catchy hook, sing-along chorus
white noise, lo-fi loop, vinyl crackle, tape hiss
bright major chord, C major, A major, major key
古筝 solo, guzheng solo, 琵琶 solo, pipa solo, 笛子 solo, dizi solo, 二胡 solo, erhu solo
戏腔, 京剧, 京劇, 戏曲, 越剧, 黄梅戏, opera vocal, belting
高音飙歌, 海豚音, whistle register, 维塔斯, Vitas-style
MCSC 喊麦, 电音喊麦, Chinese EDM shout, 网络流行语, meme phrase
```

**8 行 = 5 类 (Drums / Structure / Loop / Key / 中文污染) 必填**。

---

## 7. 5 项测试汇总 Pass/Fail 表

| # | 测试项 | Pass 阈值 | 4 段基线 | 决策 |
|---|---|---|---|---|
| 1 | 中文 vocal 发音 | CER < 15% | [待跑] | ☐ Pass / ☐ Fail |
| 2 | 8 段结构服从 | ≥ 75% (3/4) | [待跑] | ☐ Pass / ☐ Fail |
| 3 | 中文意象识别 | ≥ 75% (3/4) | [待跑] | ☐ Pass / ☐ Fail |
| 4 | 中文情感对位 | ≥ 75% (3/4) | [待跑] | ☐ Pass / ☐ Fail |
| 5 | 中文污染压制 | 污染率 ≤ 25% (1/4) | [待跑] | ☐ Pass / ☐ Fail |

### 总判定
- **5/5 Pass** → Track 2 SOP v0.1 锁定, 进 Domain 2
- **4/5 Pass** → 修补 Fail 项, 复跑, 通过后锁定
- **≤ 3/5 Pass** → 暂停, 重新评估 Suno 中文能力, 可能需要 Udio 备选

---

## 8. 时间表

| 日期 | 动作 |
|---|---|
| 2026-07-11 (今天) | v0.1 文档完成 (本文件) |
| 2026-07-12 | 准备测试歌词 8 段 (≥ 400 char 终版) + 5 项测试 prompt 终版 |
| 2026-07-13 | 跑 4 段测试歌词 (基线 + Whisper transcript) |
| 2026-07-14 | 跑 16 段 (4 段 × 5 项 + 组 A 无 NP + 组 B 有 NP) |
| 2026-07-15 | 5 项测试结果汇总, 出 Pass/Fail 表 |
| 2026-07-16 | Track 2 SOP v0.1 锁定 (5/5 Pass) 或修补 (4/5 Pass) |

---

## 9. 待解决问题 (本版本未锁)

- [ ] 测试歌词扩到 ≥ 400 char (当前 ~350 char)
- [ ] Suno 中文 zh model Whisper (vs zh + en 混合)
- [ ] 5 项测试 prompt 是否需要分语言版本 (简体 zh-Hans vs 繁体 zh-Hant)
- [ ] 评估脚本 (cer_eval.py) 是否需新建, 引用已有 whisper-multiwindow.py
- [ ] Kieran 听感评分 5 维定义 (是否复用 haevo-a-r-control-table 7 维度)

---

## 10. 引用

- haevo-a-r-control-table SKILL.md (Domain 3 7 维度 + Failure Criteria)
- multi-artist-label-playbook SKILL.md v4.7 (Chinese 8 段 lyric 模板 + v4.2 Genre 矩阵)
- suno-5.5-ambient-workflow SKILL.md (Whisper multi-window 评估方法)
- multi-artist-metadata-automation references (scripts/whisper-multiwindow.py)

---

⚠️ **[草稿 v0.1, 待 Kieran 审]**

📋 **决策问题**:

1. 测试歌词扩到 ≥ 400 char 是否同意 (当前 ~350 char, 略低于阈值)
2. 5 项测试 Pass/Fail 阈值是否调整 (CER 15% / 结构服从 75% / 意象 75% / 情感 75% / 污染 25%)
3. 时间表 2026-07-13 跑测试是否同意 (vs 7-15 跑)
4. 评估脚本 cer_eval.py 是否复用已有 whisper-multiwindow.py, 还是新建