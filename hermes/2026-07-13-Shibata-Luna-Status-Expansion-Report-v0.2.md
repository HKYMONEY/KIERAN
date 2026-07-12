---
artist: Shibata Luna
artist_id: A4
status: wip
version: 0.2 (Refined after C-ROUNDA music-director review)
date: 2026-07-13
type: status-and-expansion-report
source_vault: HKYOB
sources_verified:
  - 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md
  - 八位藝人流量權重曲風映射報告.md (v2.0, 2026-07-10)
  - 市場高流量曲風缺口與發行標籤指南.md
  - skill: music/multi-artist-metadata-automation (v4.7)
  - skill: music/ai-music-artist-brand-dna (verified 2026-07-08)
feedback_sources:
  - v0.1 self-critique (3-axis report imbalance: too much production detail)
  - C-ROUNDA music-director review (LOCKED 2026-07-13):
      • Adopt: City Pop core + J-Pop+Pop Genre route + A3+A4 联名 path + 7-step SOP
      • Upgrade: City Pop 起点不是边界 → Modern Japanese Pop Universe (10 sub-genres)
      • Pivot: 80s Retro City Pop → Neo City Pop (Billie / AURORA 风空间感)
      • Add: Brand tagline + Visual DNA 9 elements + Theme DNA 14 scenes
      • Defer: A3+A4 联名 to 20 Track 后
      • Correct: 主语言 ja-only (en 受众由 A1/A2/A6/A8 覆盖)
cross_references:
  - hermes/Hermes-v2-Weini-COS-Plan-v0.1.md (SOP 流程模板)
  - 10-Projects/Music-RN-Research-2026/2026-07-11-Weini-Brand-Bible-v0.3.md (Brand Bible 拆分模板)
supersedes: hermes/2026-07-13-Shibata-Luna-Status-Expansion-Report-v0.1.md
purpose: |
  v0.2 = C-ROUNDA 拍板后的 Brand DNA 升级。
  - 定位: City Pop → Japanese Nightscape Pop Brand
  - Sound DNA: 8 TBD → 12 TBD (含 Visual + Theme + Tagline 三层新增)
  - Sub-genre 池: 单一 City Pop → Luna Universe (10 起步 + 无限扩)
  - Suno 路径: Retro 80s → Neo City Pop (Suno 5.5 Pro 现代模型优势)
  - 联名: 早期 → 20 Track 累积后
---

# Shibata Luna — 现有风格 & 可拓展风格报告 (v0.2)

## § 1. 一句话现状 (重写)

A4 **Shibata Luna** 在 Haevo Records 8 艺人矩阵里定位升级：

> **Japanese Nightscape Pop Brand** — 围绕"东京 + 凌晨 + 安静时刻"场景宇宙的现代日本流行品牌。
>
> Sound DNA 中央支柱 = Neo City Pop（City Pop 是起点不是边界），全 10 个 sub-genre 池统一品牌。
>
> 全部 Track 围绕"Adult 日本人日常生活"主题 — 夜归 / 通勤 / 便利店 / 4am，无失恋无励志无偶像。

**新定位对应算法池**：Spotify #33 City Pop → Spotify Twilights / Old School City Pop / Late Night Drive / Japanese Pop Mix + Apple Music Japan 城市歌单 + Apple Music Asia 通勤歌单。

## § 2. LOCKED 字段 (v4.7 不动 + 1 修正)

| 字段 | LOCKED 值 | 来源 |
|---|---|---|
| **ARTIST tag** | `Shibata Luna` | HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § A4 |
| **Display name** | `Shibata Luna` (无中文 alias) | multi-artist-metadata-automation SKILL v4.7 |
| **主语言** | **ja 单语言** | v0.2 修正 (en 受众由 A1/A2/A6/A8 覆盖) |
| **RouteNote Primary Genre** | `J-Pop` (39-list 内) | 多 skill 交叉 ★★★★★ |
| **RouteNote Secondary Genre** | `Pop` (39-list 内) | 同上 |
| **SUBGENRE (ID3)** | `City Pop;J-Pop` | HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § A4 ★★★★★ |
| **Catalog Prefix** | `HR-A4-T{NN}` | 同上 |
| **流量权重** | Spotify #33 City Pop | mapping 报告 § 二 |
| **发行优先级** | 🥈 P1 | mapping 报告 § 五 |
| **目标市场** | 日本 + 全球 J-Pop 受众 | 同上 |
| **SOP 复用** | Weini T02 7-step + `apply-flac-tags.py --artist A4` + `track-qc-check.py` | C-ROUNDA § 4 |
| **联名时机** | 20 Track 累积后 | C-ROUNDA § 6 |

## § 3. Brand DNA 维度展开 (v0.2 新增 3 层 = 12 字段)

按 `ai-music-artist-brand-dna` 框架，将原 Sound DNA 8 字段升级为 **12 字段 ÷ 3 大层**：

### Layer 1: Sound DNA (声音指纹 = 7 字段)

| 字段 | 状态 | 说明 |
|---|---|---|
| 3.1 Genre (主/次/三级) | ✅ LOCKED | J-Pop + Pop + Luna Universe sub-pool |
| 3.2 BPM (range + center) | ⭐ TBD | Neo City Pop 优先 90-110 |
| 3.3 Key (primary % + forbidden) | ⭐ TBD | 与 Luna Universe 池分池锁定 |
| 3.4 Length (单曲/Extended/Sync Edit) | ⭐ TBD | 3 个产品线各不同 |
| 3.5 Vocal (wet % / dry % / subtype) | ⭐ TBD | Whisper 中频女声 |
| 3.6 Frequency signature | ⭐ TBD | sub / presence / air 三层比例 |
| 3.7 Field recording (mandatory/env) | ⭐ TBD | 东京 + 通勤 + 雨天 ambient |

### Layer 1+: ⭐ v0.2 NEW — Brand 维度 (4 字段)

| 字段 | 状态 | 说明 |
|---|---|---|
| 3.8 **Brand tagline** (1 句话) | ⭐ **TBD — 待 Kieran 拍** | 3 候选见 § 7.1 |
| 3.9 **Visual DNA** (9 元素) | 🔒 **LOCKED v0.2** | 东京 / 凌晨 / 蓝 / 玻璃反光 / 暖灯 / 女孩 / 雨 / 35mm 胶片 / 浅景深 |
| 3.10 **Theme DNA** (14 场景) | 🔒 **LOCKED v0.2** | 夜归 / 通勤 / 雨 / 夏天 / 电车 / 东京 / 便利店 / 咖啡 / 回忆 / 4am / 海边 / 黄昏 / 信号灯 / 等人 |
| 3.11 **Nightscape framing** | 🔒 **LOCKED v0.2** | "Japanese Nightscape Pop" 情绪世界观 (Night / Lonely / City / Dream 4 keyword 池) |

### Layer 2: Forbidden DNA (禁止 7 字段)

| 字段 | 状态 |
|---|---|
| 3.12 Drum policy (禁 EDM/trap/hi-hat, 允许 cinematic pulse/heartbeat) | ⭐ TBD |
| 3.13 Key policy (禁 bright major / C major) | ⭐ TBD |
| 3.14 Structure policy (禁 radio verse-chorus-verse) | ⭐ TBD |
| 3.15 Vocal policy (禁 dry pop vocal / ghost voice) | ⭐ TBD |
| 3.16 Field recording policy (禁 nature documentary / sleep channel) | ⭐ TBD |
| 3.17 Suno negative prompt (≥8 行) | ⭐ TBD（可复用 Haevo/Weini 基底） |
| **3.18 v0.2 NEW — 负向品牌 DNA** | 🔒 **LOCKED v0.2** 禁：失恋 / 励志 / 偶像 / 廉价 80s 复古乐器 (Bass/Rhodes/Brass) |

### Layer 3: Business DNA (商业 6 字段)

| 字段 | 状态 |
|---|---|
| 3.19 Per-release 5-product matrix | ⭐ TBD |
| 3.20 12-month roadmap (D+5 / D+28 / D+88) | ⭐ TBD |
| 3.21 Platform priority (RouteNote + Spotify Editorial Japan / Apple Music Asia) | ⭐ TBD |
| 3.22 Revenue model (per-track 5-year projection) | ⭐ TBD |
| 3.23 **Brand positioning statement** (1 行) | 🔒 **LOCKED v0.2** = "Japanese Nightscape Pop Brand" |
| 3.24 Audience recognition layer (5 秒内识别 = Layer A 数字 + Layer B 情绪 + Layer C 配器) | ⭐ TBD |

**总进度**（22 个字段）：
- ✅ LOCKED = 6 (Genere/Subgenre/Catalog + Visual/Theme/Nightscape + Positioning + 负向品牌)
- ⭐ TBD = 16

## § 4. Track 历史 (不变 = 全空)

| 维度 | 现状 |
|---|---|
| Track 1 / Lyrics / Suno Prompt / Playbook | ❌ 全部未生成 |
| Suno 测试 A1-A4 (5.5 Pro 实验) | ❌ 未跑 |
| Whisper 转录 + 5 维评分 | ❌ 无 |
| RouteNote / Spotify 投稿历史 | ❌ 无 |

## § 5. Luna Universe (v0.2 主重写)

### 5.1 Sub-genre 池 (10 个 LOCKED v0.2，可无限扩)

| # | Sub-genre | Suno 5.5 适配度 | Luna 应用 % |
|---|---|---|---|
| 1 | **Neo City Pop** ⭐ priority 1 | ✅ 现代乐器空间感强 | 30% (Anchor) |
| 2 | City Pop (经典, 80s Retro) | ⚠️ Bass/Rhodes/Brass 易廉价 | 5% (仅 1-2 首试作) |
| 3 | Dream Pop | ✅ AURORA 风 | 15% |
| 4 | Bedroom Pop | ✅ 现代 lo-fi 基础 | 10% |
| 5 | Indie Pop | ✅ 适中 | 10% |
| 6 | Ambient Pop | ✅ 留白多 | 10% |
| 7 | Chill Pop | ✅ 现代 | 5% |
| 8 | Lo-fi Pop | ✅ 现代温暖 | 10% |
| 9 | Anime Ballad | ✅ 日本传统 | 5% (Track 2+ 试) |
| 10 | Piano Pop | ✅ 古典底 | 5% |
| **未来可加** | Night Pop / Rain Pop / Memory Pop / Acoustic Night |  |  |

### 5.2 Suno 5.5 Pro 路径优先级 (LOCKED)

| 优先级 | 路径 | 决定 |
|---|---|---|
| 1 | **Neo City Pop** | ✅ 优先 |
| 2 | Billie 风空间感 + female vocal + soft synth | ✅ Track 1 v0.1 Suno Prompt |
| X | Retro 80s (山地達郎 / 杏里) | ❌ **REJECTED** — 乐器廉价风险，C-ROUNDA § 2 拍板 |

### 5.3 Visual DNA 9 元素 (LOCKED v0.2)

全部 Luna Cover 一致：

```
[0] Tokyo 城市背景（Tokyo Tower / 涩谷十字 / 山手线电车）
[1] Late night 时间感（凌晨 12-4am 主调）
[2] Blue 主色（蓝调夜色）
[3] Glass reflection（玻璃反光，地铁车窗 / 高楼幕墙）
[4] Warm lamp 点光源（暖灯，居酒屋 / 便利店 / 路灯）
[5] Girl 主体（女性背影或侧脸，不露正面 = universal international 代入）
[6] Rain 天气（雨 / 雨后湿地面）
[7] 35mm film grain（胶片颗粒感）
[8] Shallow depth of field（浅景深）
```

### 5.4 Theme DNA 14 场景 (LOCKED v0.2)

歌词允许出现的"成年人日常"主题池：

```
夜归 / 通勤 / 雨 / 夏天 / 电车 / 东京 / 便利店 / 咖啡 / 回忆 /
4am / 海边 / 黄昏 / 信号灯 / 等人
```

**禁**：失恋 / 励志 / 偶像 / 公主梦 / 校园纯爱。

### 5.5 品牌一句话 (Lock 后填)

当前 ⭐ TBD，3 候选见 § 7.1。

## § 6. Brand Bible v0.1 → v1.0 路线图 (升级 v0.2)

| 步骤 | 文件 / 动作 | 依赖 | 估计工作量 |
|---|---|---|---|
| **6.1** | 拍 § 7.1 Brand tagline (3 选 1 或你给 1 句) | — | 5 分钟 |
| **6.2** | 我建 `10-Projects/Music-RN-Research-2026/A4-Shibata-Luna-Brand-Bible-v0.1.md` | 6.1 | 中 (12 节) |
| **6.3** | Sound DNA 7 字段 (BPM/Key/Length/Vocal/Frequency/Field) 你给数字 | — | 5 分钟 |
| **6.4** | Forbidden DNA 6 字段 (Drum/Key/Structure/Vocal/Field/Suno Negative) 你给列表 | — | 5 分钟 |
| **6.5** | Suno 5.5 Pro 跑 A1-A4 (10 sub-genre 各 1 段) | 6.3 + 6.4 | 中 |
| **6.6** | Whisper 转录 + 5 维评分选 Best 3 段 | 6.5 | 中 |
| **6.7** | Best 3 段 → Suno Extend 到 4:00 single | 6.6 | 小 |
| **6.8** | `track-qc-check.py` 母带 QC + 28 tag 写入 | 6.7 | 中 |
| **6.9** | Track 1 Suno Prompt v1.0 + Lyrics v1.0 + Cover v1.0 | 6.8 | 中 |
| **6.10** | **Brand Bible v1.0 LOCK** + Track 01 Playbook v0.1 | 6.9 | 小 |
| **6.11 ⭐ v0.2 NEW — Visual Brand Bible lock** (9 元素 100 Track 统一) | 6.2 | 小 |
| **6.12 ⭐ v0.2 NEW — Theme DNA 14 场景锁版** | 6.2 | 小 |
| **6.13** | Luna Track 2-10 (新 9 sub-genre 各 1) | 6.10 | 大 (周计) |
| **6.14 ⭐ 推迟条件** | 6.13 后才允许 A3+A4 联名 | 6.13 | — |

⚠️ **关键风险**：无 Sound DNA 时不能生成 Track 1。6.1 + 6.3 + 6.4 是必需起点。

## § 7. 决策清单 (LOCKED 拍板)

### 7.1 Brand tagline (⭐ TBD → 你拍 1 句)

| 候选 | 文字 |
|---|---|
| ① | "She sings the quiet moments between midnight trains and first light." |
| ② | "Every song feels like Tokyo after the rain." |
| ③ | "Memories hidden inside neon reflections." |
| ④ | 你自己写 |

回 1 行我做。**v0.2 整个报告的最后一个 TBD**。

### 7.2 Luna Universe 池起步数 ✅ LOCKED v0.2

**10 个全开** — Neo City Pop (anchor) + City Pop + Dream Pop + Bedroom Pop + Indie Pop + Ambient Pop + Chill Pop + Lo-fi Pop + Anime Ballad + Piano Pop + **未来可加 Night Pop / Rain Pop / Memory Pop 等**。

### 7.3 A3+A4 联名时机 ✅ LOCKED v0.2

**Luna 累积 20 首作品后**（不是早期）。

---

## § 8. Brand DNA 3 层契约 (LOCKED 模板)

参考 `ai-music-artist-brand-dna` skill + 你 7/11 LOCKED 文档分离 discipline：

### 文档分离

| 文档 | 目的 | 时间范畴 | 更新频率 |
|---|---|---|---|
| **Brand Bible** (e.g. `A4-Shibata-Luna-Brand-Bible-v1.0.md`) | 永久 + 慢演化 + 快迭代品牌规则 | 多年 (跨所有 Track) | Permanent: never / Slow: 每季 / Fast: 每首 |
| **Track Playbook** (e.g. `A4-Shibata-Luna-Track-01-Playbook-v0.1.md`) | 单 Track 具体 SOP (prompt / lyric / mastering / metadata) | 单 Track (一次) | Archive 后 v0.1 → v1.0 周期 |

### Brand Bible 3 个 Knowledge 层 (跨版本 LOCKED)

| Knowledge 层 | 时间常数 | 例子 |
|---|---|---|
| **Permanent** (Permanent DNA) | 不重建不更新 | Brand tagline, Mission, Visual DNA 核心元素, 禁流派 |
| **Slow Evolution** (Slow DNA) | 每季重评 | Luna Universe 池扩/收缩, BPM range, Key pool, Master LUFS/TP |
| **Fast Iteration** (Fast DNA) | 每 Track | Suno Prompt specifics, Cover art, Editorial pitch |

### Confidence ★ 系统 (Kieran 7/11 LOCKED)

| 源 | 默认 ★ |
|---|---|
| Spotify / Apple Music / RouteNote 官方 | ★★★★★ |
| Soundcharts / LANDR / DistroMono industry report | ★★★★☆ |
| Hermes 100+ tracks data | ★★★★☆ |
| Revelator / Playlist Pilot / LANDR blog | ★★★☆☆ |
| Reddit / Twitter | ★★☆☆☆ |

当前 v0.2 Luna 规则 Confidence：Locked 项 ★★★☆☆ (genres LOCKED ★★★★★ — 但 Sound DNA 整体未测过)。

---

## § 9. AI Update Log + C-ROUNDA feedback 总结

### 9.1 AI Update Log

```
2026-07-13  v0.2 报告基于：
  - Suno 5.5 Pro (verified 2026-07-08): 现代乐器空间感强
                   Retro 80s 乐器廉价风险高
  - Spotify Editorial (verified 2026-06-27):
      - Old School City Pop (37i9dQZF1DX8E00BUElVpN)
      - Twilights (37i9dQZF1DX3Ogo9pFvBkY)
  - RouteNote v4.2 (verified 2026-07-01):
      - 39-list dropdown LOCKED
      - Shibata Luna = J-Pop + Pop
```

### 9.2 C-ROUNDA feedback summary

| § 主题 | C-ROUNDA 输入 | v0.2 采纳 |
|---|---|---|
| § 1 元数据 | Genre 不改 LOCKED | ✅ |
| § 2 风格 | 候选 β 现代 → Neo City Pop 优先 | ✅ |
| § 2 Sound DNA 多维 | "艺人宪法" 升维 | ✅ |
| § 2 City Pop 太窄 | 现代日本流行宇宙 | ✅ |
| § 3 跨艺人联名时机 | 20 首后 | ✅ |
| § 4 SOP + 工具链 | 沿用 Weini T02 | ✅ |
| § 5 视觉统一 | 东京凌晨蓝 9 元素 | ✅ |
| § 5 歌词成人向 | 14 场景池 | ✅ |
| § 5 Brand tagline | 1 句话 | ⭐ TBD |
| § 5 定位重定义 | Japanese Nightscape Pop | ✅ |

---

## § 10. Lessons Learned (升级 v0.2)

1. **空 vault 报告必须等数据，别列具体优化路径**：v0.1 我在 0 值 Sound DNA 时长篇讨论 80s vs 现代 City Pop — 这是越权。**v0.2 把 Style Path 改成 C-ROUNDA 拍板的明确选项**。
2. **视觉 DNA 必须 Brand DNA 同帧评估**：v0.1 完全漏视觉。**v0.2 把 Visual DNA 加入 Layer 1+** 与 Sound/Theme 平级。
3. **City Pop 不是品类，是场景宇宙的"锚"**：v0.1 把 City Pop 当 genre。**v0.2 升级为 Japanese Nightscape Pop Brand = 氛围/场景定位**（与 Haevo "Cinematic Ambient Universe" 同构）。
4. **Sun0 Retro 80s = 高风险路径**：v0.1 列候选 α 看似稳。**C-ROUNDA 揭示 Suno 5.5 Pro 在 Bass/Rhodes/Brass 易廉价** — 升级为 Neo City Pop 优先。
5. **唯一日语艺人 = 反而是品牌资产不是限制**：v0.1 列"唯一日语艺人"是中性。**v0.2 重新框架为"独占日本窗口 + 跨艺人大陆 en 受众由 A1/A2/A6/A8 覆盖"** — 形成"日本窗口 × 英语世界" 的双艺人协同。
6. **Brand Bible 模板必须 3 层 Brand DNA 同步填**：v0.1 7 个 TBD 全堆在 Sound。**v0.2 升 22 字段 ÷ 3 层 = Sound 7 + Brand 4 + Forbidden 6 + Business 5** — 不漏任何维度。
7. **联动时机推迟，避免算法稀释**：v0.1 列"A3+A4 联名 = 早期可做"。**C-ROUNDA 揭示 Spotify 算法对 0 累积艺人联名 = 互相稀释 — 升级为 20 Track 累积后**。
8. **Confidence ★ 系统必须跨多源交叉验证**：v0.1 单源 ★★★。**v0.2 已 LOCKED 项 ★★★★★ (RouteNote 官方)，TBD 项 ★★☆☆☆**。

---

## § 11. Decision Summary (Kieran 拍板 1 行)

| § | 项 | 状态 | 需 Kieran |
|---|---|---|---|
| Genre Primary | J-Pop | 🔒 | — |
| Genre Secondary | Pop | 🔒 | — |
| 主语言 | ja 单语言 | 🔒 v0.2 | — |
| 定位 | Japanese Nightscape Pop Brand | 🔒 v0.2 | — |
| Luna Universe 池 | 10 个 + 未来扩 | 🔒 v0.2 | — |
| 路径优先 | Neo City Pop (1st) | 🔒 v0.2 | — |
| Visual DNA 9 元素 | 全列 | 🔒 v0.2 | — |
| Theme DNA 14 场景 | 全列 | 🔒 v0.2 | — |
| Forbidden DNA 负面 | 廉价 80s 乐器 / 失恋励志偶像 | 🔒 v0.2 | — |
| 联名时机 | 20 Track 后 | 🔒 v0.2 | — |
| 主语言副语言 | **移除** en (en 由 A1/A2/A6/A8 覆盖) | 🔒 v0.2 | — |
| **Brand tagline** | ⭐ **TBD** | ⭐ | ✅ 拍 3 选 1 |

**唯一未拍 = Brand tagline**。

回 1 行我做 v0.3 (tagline 锁定 → 3 层 Brand DNA 数字确定 → Track 1 Suno Prompt)。
