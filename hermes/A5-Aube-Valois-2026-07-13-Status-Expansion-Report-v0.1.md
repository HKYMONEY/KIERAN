---
artist: Aube Valois
artist_id: A5
status: wip
confidence: ★★★☆☆
type: status-and-expansion-report
date: 2026-07-13
source_vault: HKYOB
sources_verified:
  - /var/codex_project/hermes-home/profiles/bot-b/notes/haevo_records_8_artists_v4.5.md
  - /root/obsidian-sync/八位藝人流量權重曲風映射報告.md
  - /var/codex_project/hermes-home/profiles/bot-b/skills/music/multi-artist-metadata-automation/templates/haevo_records_metadata_v4.5.json.template
external_research:
  - https://en.wikipedia.org/wiki/French_chanson
  - https://en.wikipedia.org/wiki/French_pop
  - https://en.wikipedia.org/wiki/Alternative_pop
cross_references:
  - skills/music/ai-music-artist-brand-dna/SKILL.md (9 Sound DNA field template)
  - skills/music/multi-artist-metadata-automation/SKILL.md (v4.7 11-field pattern)
  - skills/hk-status-expansion-report-flow/SKILL.md (Status report pattern)
purpose: A5 现状 + 可拓展风格一次性收口，给 Kieran 拍 Sound DNA 前的决策底
---

# Aube Valois — Status + Expansion Report v0.1

## 1. 一句话现状

A5 Aube Valois 是厂牌 8 艺人里**法语矩阵**唯一代表，**路由端 11 字段已 LOCKED (v4.5, 2026-07-08 Kieran 拍板)**，**Sound DNA 9 字段全 TBD**，**Track 历史 0**，处于 Brand Bible v0.0 raw material 状态。本报告 = 流派学事实 + LOCKED 字段 + 决策清单，不含任何 Aube 自创数字。

## 2. v4.7 LOCKED 字段（11 项路由端 — 不可改动）

| # | 字段 | 值 | 来源 |
|---|------|-----|------|
| 1 | display_name | `Aube Valois` | v4.5 § artists.Aube |
| 2 | language | `fr-FR` | v4.5 |
| 3 | routenote_main_genre | `French Pop` | v4.5 + RN 39-list 合规 |
| 4 | routenote_secondary_genre | `Pop` | v4.5 |
| 5 | v3_main_genre | `French Pop` | v4.5 |
| 6 | v3_secondary_genre | `Chanson;Alternative Pop` | v4.5 |
| 7 | subgenre | `French Chanson;Alternative Pop;Ambient Electronic` | v4.5 |
| 8 | isrc_prefix | `HKXIA2026AUB` | v4.5 |
| 9 | filename_patterns | `*Aube*` / `*Premier*` / `*Matin*` / `*AUBE*` | v4.5 |
| 10 | track_alpha_offset | 0 | v4.5 |
| 11 | 流量权重重叠区 | `#29-35 (Pop 类别)` | 八位藝人流量權重曲風映射報告 § 1 |

**子流派学事实 (Wikipedia 公开源，非编造)：**

- **Chanson** — 字面 "song"，但流派学狭义指 1950-60s 法国流行音乐；起源于 troubadours 单声部传统 + 19 世纪蒙马特 café-concert / cabaret 现实主义 (`chanson réaliste`，以 Piaf 为代表)。文学性强 + 叙事化 + 钢琴/弦乐主导。
- **French Pop** — 起源于 1950s；yé-yé (1960s Françoise Hardy 风格) → 1990s M83 / Phoenix / Air / Daft Punk → 2020s Stromae / Angèle。Wikipedia 列入 1990s 名单：**Air, -M-, Lara Fabian, Lynda Lemay, Louise Attaque, Mano Solo, Pascal Obispo, Axelle Red, Phoenix**。
- **Alternative Pop** — Wikipedia 定义："pop music with broad commercial appeal that is made by figures outside the mainstream, or which is considered more original, challenging, or eclectic than traditional pop music"。起源：1980s-2000s UK，roots = pop + alternative rock + R&B + electronic + dream pop + indie pop + art pop + synth-pop。

**Aube 三标签组合解读 (LOCKED，不是建议)：** Chanson 提供歌词/叙事骨 + French Pop 提供法语市场可达性 + Alternative Pop 给她"非主流但有商业潜力"的入口。这是**矩阵差异化**，不是 Sound DNA。

## 3. Sound DNA 9 字段 TBD（全空，待 Kieran 拍）

| # | 字段 | 状态 | 缺失影响 |
|---|------|------|----------|
| 1 | Key (主调) | ⭐ TBD | Suno prompt 无法跑 |
| 2 | BPM 范围 | ⭐ TBD | Suno prompt 无法跑 |
| 3 | Vocal subtype (whisper/breathy/bel canto/spoken) | ⭐ TBD | Lyric SOP 无法定 |
| 4 | Wet/Dry ratio | ⭐ TBD | Master 母带策略无法定 |
| 5 | Field recording (层 + 类型 + 占比) | ⭐ TBD | Cinematic texture 无法做 |
| 6 | Forbidden patterns (拒绝清单) | ⭐ TBD | Suno 排除规则无法写 |
| 7 | Track 长度策略 (Spotify 4-6 / YT 1h / Sleep 8h) | ⭐ TBD | 商业矩阵无法定 |
| 8 | Visual identity (色板 / 镜头 / 服装) | ⭐ TBD | Cover 提示词无法写 |
| 9 | One-liner tagline | ⭐ TBD | Brand 故事无法讲 |

> ⚠️ Kieran Pitfall 8 (LOCKED)：**禁止用"类似艺人" (Veloria Senda / Shibata Luna) 的数字填 Aube TBD**。每个 TBD 必须 Aube 单独拍。

## 4. Track 历史 (4 维度全空)

| 维度 | 状态 |
|------|------|
| 已发行 Track | 0 |
| Track Playbook | 0 |
| Brand Bible | 0 |
| Spotify / Apple claim | N/A |

A5 = Haevo Records 第 6 顺位开发的艺人（按 v4.7 8 艺人矩阵 / v4.5 16 章文档）。

## 5. 可拓展风格方向 (inference, not measured)

下列均为**流派学推论**，不是 Aube 已锁定方向。Kieran 不拍 = 不算。

| 方向 | 流派学依据 | Suno Prompt 候选 | 母带建议 |
|------|-----------|----------------|---------|
| **A. 蒙马特香颂** | Chanson réaliste 文学叙事传统 (Piaf / Brel) | acoustic piano + breathy female fr-FR vocal + minimal strings | -16 LUFS / dynamic range wide |
| **B. 90s 法式梦幻流行** | Air / M83 / Phoenix 谱系 (Wikipedia 1990s 名单) | dream pop guitar + shoegaze reverb + whispered fr-FR + analog synth pad | -14 LUFS / 主流 streaming |
| **C. 当代法式电子** | Stromae / Angèle 谱系 (Wikipedia 2020s 名单) | electronic beat (限制) + melodic fr-FR vocal + synth-pop | -12 LUFS / club 适配 |
| **D. 法语 Ambient** | 子流派已 LOCKED `Ambient Electronic` 但权重最低 | ambient pad + far-field fr-FR whisper + field recording Paris rain | -17 LUFS / Haevo 同系 |

**4 方向关系 (供参考)：**

- A = 文学/叙事最重 / B = 厂牌差异化最强 (90s 复古不撞 Veloria 西语) / C = 流量天花板最高 (Stromae 级) / D = 与 Haevo 主理人共系但风险 = 失去法语辨识度

## 6. Brand Bible v0.1 → v1.0 路线图 (估计工作量)

| 步骤 | 内容 | 估时 |
|------|------|------|
| 1 | Kieran 拍 9 字段 Sound DNA (本报告决策清单 § 7) | 30 min |
| 2 | Suno prompt v0.1 跑 Round 1 (4-8 段) | 2 天 |
| 3 | A&R 7 维评分 + 选 Best ≥ 85 | 1 天 |
| 4 | Track 1 锁定 (T01 title / BPM / Key / 长度 / structure) | 1 天 |
| 5 | 母带 + LUFS + LRA + TP 4 指标测 | 1 天 |
| 6 | Cover 3000×3000 (image_gen 4 候选) | 2 天 |
| 7 | 元数据 + ID3 31 字段 + RouteNote 提交 | 1 天 |
| 8 | Brand Bible v0.5 写完 (16 章 + 3 层 DNA) | 2 天 |
| 9 | A/B Cover 测试 + 流量追踪 30 天 | 30 天 |
| 10 | v1.0 LOCKED + 12-month business 矩阵 | 1 天 |

**总计：** Sound DNA 拍板日 → Track 1 锁定 ~ 7 工作日 → v1.0 ~ 5 周 (含 30 天数据窗口)

## 7. 决策清单 (1 字段 1 行, 共 7 项)

| # | 决策项 | 选项 | 推荐 |
|---|--------|------|------|
| 7.1 | 主推方向 | A 蒙马特 / B 90s 梦幻 / C 当代电子 / D 法语 Ambient | **B** (厂牌差异化最强, 不撞 Veloria) |
| 7.2 | 主调 Key | (待 Kieran 拍, 不要用 Veloria / Luna 的) | ⭐ TBD |
| 7.3 | BPM 范围 | (待 Kieran 拍) | ⭐ TBD |
| 7.4 | Vocal subtype | whisper / breathy / bel canto / spoken | ⭐ TBD |
| 7.5 | 5 产品矩阵 | 全做 5 / 只 Spotify / 加 Sync | Spotify + Instrumental (最少 2) |
| 7.6 | Visual 起点 | 蒙马特咖啡馆 / 法式公寓 / 雨夜巴黎街 / 雪夜塞纳河 | ⭐ TBD |
| 7.7 | Track 1 主题 | "Premier Matin" / "Café Noir" / "Rue de Rivoli" / 待 Kieran | ⭐ TBD |

> **回格式：** `7.1=B 7.2=Dm 7.3=70-80 7.4=breathy 7.5=Spotify+Inst 7.6=蒙马特咖啡馆 7.7=Café Noir`
> 或者回 `1=B` 只拍方向，其余我按 B 推默认。

## 8. 章节交叉引用

- § 2 LOCKED 字段 → `multi-artist-metadata-automation/SKILL.md` v4.7 11 字段 pattern
- § 3 Sound DNA TBD → `ai-music-artist-brand-dna/SKILL.md` 9 字段模板
- § 5 方向 B 候选 → `suno-5.5-ambient-workflow/SKILL.md` (反向参考, B 不是 ambient 但 prompt 工艺相通)
- § 6 步骤 2 → `haevo-a-r-control-table/SKILL.md` (4-8 段 + 7 维评分)
- § 6 步骤 6 → `haevo-cover-and-final-flac/SKILL.md` (3000×3000 流程)
- § 6 步骤 7 → `multi-artist-metadata-automation/SKILL.md` (ID3 + RouteNote SOP)

## 9. AI Update Log

- **v0.1 (2026-07-13 bot-b)** — 第 1 次写 Status + Expansion Report。LOCKED 字段来自 v4.5 + 流量映射报告 (vault grep)；流派学事实来自 Wikipedia 3 个公开页 (curl)；Sound DNA 9 字段全 TBD 不编；可拓展方向 4 条标 inference not measured；决策清单 7 项。

## 10. Lessons Learned

- A5 在 8 艺人矩阵中开发顺位靠后（v4.5 16 章），意味着 Sound DNA 没有任何先验可参考 — 必须 Kieran 单独拍，**不能从 Veloria Senda / Shibata Luna 借数字** (Pitfall 8)
- LOCKED 11 字段的 v3_secondary_genre `Chanson;Alternative Pop` + subgenre `Ambient Electronic` 三组合暗示 Aube 的差异化是 **文学叙事 × 法语市场 × 主流流行入口** — 这与 Veloria 的"民俗根"和 Luna 的"东京夜归"完全不同
- 流量权重 #29-35 (Pop 类别) 意味着 Aube 流量天花板比 Veloria (#44-47) 高，但比 Shibata Luna (#33 City Pop) 区域更拥挤 — 主推方向选 B (90s 法式梦幻) 比 C (当代电子) 差异化更强
- Wikipedia 流派学上 "Alternative Pop" 在 2020s 大量与 dream pop / shoegaze 重叠 — 这给了 B 方向工艺上的可行性 (Suno 5.5 对 dream pop guitar + reverb 处理成熟)

---

**接下来你用这个 report 做什么 (1-2 句)：**
回 § 7 决策清单任意 1 项，我立刻更新 A5 Sound DNA。回 0 我不动。