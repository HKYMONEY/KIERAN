---
artist: Shibata Luna
artist_id: A4
status: wip
confidence: ★★★☆☆ (genres LOCKED ★★★★★, Sound DNA TBD ★★)
type: status-and-expansion-report
date: 2026-07-13
source_vault: HKYOB
sources_verified:
  - 30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md
  - 八位藝人流量權重曲風映射報告.md (v2.0, 2026-07-10)
  - 市場高流量曲風缺口與發行標籤指南.md
  - skill: multi-artist-metadata-automation (v4.7)
  - skill: ai-music-artist-brand-dna
cross_references:
  - hermes/Hermes-v2-Weini-COS-Plan-v0.1.md (SOP 流程模板)
  - 10-Projects/Music-RN-Research-2026/2026-07-11-Weini-Brand-Bible-v0.3.md (Brand Bible 模板)
purpose: |
  摸清 Shibata Luna (A4) 在 Haevo Records 8 艺人矩阵中的现有状态，
  列出 v4.7 已 LOCKED 字段 + Sound DNA 空缺字段 + 可拓展风格方向，
  为 Brand Bible v0.1 + Track 1 生成提供决策清单。
---

# Shibata Luna — 现有风格 & 可拓展风格报告 (v0.1)

## § 1. 一句话现状

A4 **Shibata Luna** 是 Haevo Records 8 艺人里**唯一日语艺人**，定位 **City Pop / J-Pop**（Spotify 算法 #33 City Pop 池），🥈 P1 优先级，目标市场 = 日本 + 全球 J-Pop 受众。**Genre 路由端 100% 完整 LOCKED（v4.7）**，**Sound DNA 端完全空白**——vault 里**没有 Luna 的 Brand Bible、Track Playbook、Suno 测试历史**。

## § 2. 已 LOCKED 字段（v4.7 官方映射 — 不需要再决策）

| 字段 | LOCKED 值 | 来源 |
|---|---|---|
| **ARTIST tag** | `Shibata Luna` | HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § A4 |
| **Display name** | `Shibata Luna`（无中文 alias）| multi-artist-metadata-automation SKILL v4.7 |
| **主语言** | ja（主）+ en（副） | mapping 报告 |
| **RouteNote Primary Genre** | `J-Pop` (39-list 内) | 多 skill 交叉验证 ★★★★★ |
| **RouteNote Secondary Genre** | `Pop` (39-list 内) | 同上 |
| **SUBGENRE (ID3)** | `City Pop;J-Pop` | HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md § A4 ★★★★★ |
| **Catalog Prefix** | `HR-A4-T{NN}` | 同上 |
| **流量权重** | Spotify #33 City Pop | mapping 报告 § 二 |
| **发行优先级** | 🥈 P1（与 Veloria Senda + Lune Veya 同级） | mapping 报告 § 五 |
| **目标市场** | 日本 + 全球 J-Pop 受众 | 同上 |
| **8 艺人排序** | A4 / 第 4 位 | HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md |

⚠️ **LOCKED 的含义**：这 11 项**不能再改**，Tracks 1-99 必须按这个组合路由 RouteNote / Spotify / Apple Music。

## § 3. Sound DNA 字段 — **完全空白**（vault 没数据）

按 `ai-music-artist-brand-dna` skill 模板，Sound DNA 必须含 9 个字段。当前 vault 状态：

| 字段 | 状态 | 缺失影响 |
|---|---|---|
| 3.1 **Genre (主/次/三级)** | ✅ LOCKED (v4.7) | — |
| 3.2 **BPM (range + center)** | ⭐ TBD（待 Kieran 拍）| Suno Prompt 写不出具体数 |
| 3.3 **Key (primary % + forbidden list)** | ⭐ TBD | 母带 pitch shift 目标不知 |
| 3.4 **Length (单曲 / Extended / Sync Edit)** | ⭐ TBD | Suno 长度策略不定 |
| 3.5 **Vocal (wet % / dry % / subtype %)** | ⭐ TBD | "复古女声 / whisper / 中音" 哪种没拍 |
| 3.6 **Frequency signature** | ⭐ TBD | 子低频 / presence / air 比例 |
| 3.7 **Field Recording（强制/可选 + 类型）** | ⭐ TBD | 真 City Pop = Tokyo 街景？山手线？ |
| 3.8 **Brand tagline** | ⭐ TBD | "Voice inside neon rain" 等 1 行定位 |
| 3.9 **Forbidden DNA** | ⭐ TBD | 不能写 Brand Bible 8-line 负向 prompt |

⚠️ **这 8 个 TBD 字段 = Brand Bible v0.1 的核心内容**。没它就不能生成 Suno Prompt、不能跑 Track 1。

## § 4. Track 历史 — **空白**

| 维度 | 现状 |
|---|---|
| Track 1 Lyrics / Suno Prompt / Playbook | ❌ 全部未生成 |
| Suno 测试 A1-A4 (5.5 Pro 试验) | ❌ 未跑 |
| Whisper 转录 / 5 维听感评分 | ❌ 无 |
| RouteNote / Spotify Editorial 投稿历史 | ❌ 无 |

**对比**：Weini (A3) 已完成 Track 02 窗与灯，6/6 听感 PASS，In Review 状态。

## § 5. 可拓展风格方向 — 基于市场数据推断

### 5.1 流量端优化空间

| LOCKED 现状 | 可拓展点 | 数据来源 |
|---|---|---|
| Spotify #33 City Pop 算法池 = 中等流量 | Subgenre 可叠加：`City Pop;J-Pop;Retro Pop` 走 Spotify 后台标签（官方映射报告 § 4.2 已建议）| mapping 报告 § 4.2 |
| Luna 是唯一 ja 语言艺人 | 🌟 **A3 Weini + A4 Luna 双艺人 ja+zh-Hant 联名 Track** = 双算法池 #29 Mandopop + #33 City Pop 同时受益（这是 8 艺人里唯一能做跨语种的市场口）| 推断 |
| Spotify Editorial "Old School City Pop" 已有 playlist `37i9dQZF1DX8E00BUElVpN` | 🌟 Luna Track 1 可作为 editorial pitch 候选（需要 Brand Bible 锁定 Retro Pop 风格）| Spotify Editorial |
| 算法流量池波动大（City Pop 30-50 岁粉丝稳定）| 长尾 Save Rate 通常优于算法——适合 Luna Track 2/3/4 做功能型延展（夜跑 / 通勤 / 居家）| 推断 |

### 5.2 母带 + 流程端可借鉴（Weini T02 LOCKED 7 步验证）

| 已 LOCKED 工具（可用）| Luna Track 1 适用度 |
|---|---|
| `apply-flac-tags.py` 参数化 v4.7 8 艺人写入 | ✅ 直接可用（`--artist A4`）|
| `track-qc-check.py` 母带 QC 8 类 27 项 | ✅ 通用 |
| `AUDIO-QC-STANDARD-v1.0.md` 母带 8 类 27 项 + 3 路由分档 | ✅ 通用 |
| `Suno 5.5 音樂生成效能分析指南.md` (HKYOB 根) | ✅ 通用 |
| Suno 5.5 Pro `EXTENDED ambient composition` Style 字段突破 90s 默认 | ✅ 通用（City Pop 4-6 min 可能需要）|
| Weini T02 SOP 7 步验证流程 | ✅ 改 4 字段复用（Genre/Subgenre/Lang/Catalog）|

### 5.3 Suno Prompt 方向（**2 个候选子风格，未拍板**）

⚠️ 下列 2 个方向是基于"City Pop" + "J-Pop" 母风格的**候选分支**，不是 LOCKED：

#### 候选 α：复古 City Pop（80s 山下达郎 / 竹内まりや内核）

- Style 重点：analog synth bass、rhodes electric piano、drum machine LinnDrum
- 建议 BPM range：100-115
- 建议 Key pool：F#m / Am / Cmaj
- 风险：Suno 5.5 Pro 对 Vintage City Pop 适配度需测试（vault 无历史数据）
- 适合 Track 1：作为 Luna 风格基准，验证 Suno 能否稳定输出

#### 候选 β：现代 City Pop 内核（Yuki Sahashi / 竹内まりや ver.x）

- Style 重点：modern lo-fi + J-Pop chorus + breathy whisper vocal
- 建议 BPM range：90-105
- 建议 Key pool：Em / Gmaj / Bm
- 风险：与候选 α 容易混淆（如果选错 Track 1 = 后面 30 Track 全错）
- 适合 Track 1：作为 Luna 风格细分（如果 α 太 generic）

⚠️ **这两个候选我都没真值——基于 vault LOCKED + skill 推荐模式推断，不是实测**。

## § 6. Brand Bible v0.1 → v1.0 路线图（推荐执行顺序）

按 `ai-music-artist-brand-dna` skill "Brand before Catalog" 原则：

| 步骤 | 文件 / 动作 | 依赖 | 估计工作量 |
|---|---|---|---|
| **6.1** | 拍板 § 3 8 个 TBD 字段（你 1 行 1 字段给我）| — | 5 分钟 |
| **6.2** | 我建 `10-Projects/Music-RN-Research-2026/A4-Shibata-Luna-Brand-Bible-v0.1.md` | 6.1 完成 | 中 |
| **6.3** | 写 Suno Prompt v0.1（基于 6.2 Brand Bible）| 6.2 | 小 |
| **6.4** | Suno 5.5 Pro 跑 A1-A4 试作（4 段输出） | 6.3 | 中（vpn 0 成本） |
| **6.5** | Whisper 转录 + 5 维评分选 Best | 6.4 | 中 |
| **6.6** | Best 段 → Suno Extend 到 4:00-4:30 | 6.5 选定 | 小 |
| **6.7** | Track 1 母带 → `track-qc-check.py` 验证 | 6.6 | 中 |
| **6.8** | **Brand Bible v1.0 lock** + Track 01 Playbook v0.1 | 6.7 | 小 |
| **6.9** | Track 01 Suno Prompt v1.0 + Lyrics v1.0 + Cover | 6.8 | 中 |
| **6.10** | `apply-flac-tags.py --artist A4` + RouteNote 28 tag 写入 | 6.9 | 小 |

⚠️ **6.1 是必需起点**，没有它后面的全是空中楼阁。

## § 7. 推荐决策清单（你最低限度拍）

按"少而精"哲学 + 1 行答 1 字段：

| § | 字段 | 选项 |
|---|---|---|
| 7.1 | 候选风格 (α / β / 别的) | `α复古` / `β现代` / `α+β混合` / `其他你说` |
| 7.2 | BPM range | 给一个区间（如 `100-115`）或 `你推荐` |
| 7.3 | Key pool | 给一个清单（如 `F#m / Am / Cmaj`）或 `你推荐` |
| 7.4 | Vocal 类型 | `whisper` / `breathy` / `中音女声` / `alto` / `其他` |
| 7.5 | Field Recording（强制/可选）| `强制 Tokyo rain` / `强制 山手线` / `可选` / `其他` |
| 7.6 | Track 1 长度 | `3:30 single` / `4:30 single` / `6:00 ambient` / `其他` |
| 7.7 | Brand tagline（1 行）| 你给我 1 句 |
| 7.8 | Forbidden DNA（≥8 行）| 你列 / 我建议 / 其他 |

**回 7.1-7.8 任一字段我能后续推进**。回 0 行 = STOP，报告 v0.1 已存到 `hermes/` 待你 review。

---

**Kieran 听感 > 量化** — 任何字段你告诉我"我之前说过了"或"我不定"，我都不主动推。

## § 8. 章节交叉引用

- `Hermes-v2-Weini-COS-Plan-v0.1.md` — COS 9 模块通用模板
- `Weini-Brand-Bible-v0.3.md` — Brand Bible v0.3 (16章 Subgenre v0.4 拍板) 模板
- `30-Resources/FLAC-Tags/HAEVO-8-ARTISTS-FLAC-TAGS-v1.0.md` — A4 Artist Profile 完整字段
- `30-Resources/Audio-QC/AUDIO-QC-STANDARD-v1.0.md` — 母带 QC 通用标准

## § 9. AI Update Log

- 2026-07-13：v0.1 报告基于 vault LOCKED 数据 + skill 推荐模式，未跑 Suno 实验，无原始音频数据
- 2026-07-13：Genre 路由端 100% LOCKED（v4.7 多 skill 交叉验证 ★★★★★）
- 2026-07-13：Sound DNA 8 字段全 TBD ⭐——待 Kieran 拍

## § 10. Lessons Learned

1. **空 vault 的诚实摸底模式**：当 Brand Bible/Track Playbook 都不存在时，报告必须诚实标 TBD，不能用"参考 Weini"反推填默认值（违反 Pitfall 8）
2. **vault search before TBD**：本报告 § 1-4 全部基于 vault grep 实际命中，未命中即标空
3. **LOCKED vs TBD 分野必须清**：v4.7 LOCKED 数据（11 项）和 Sound DNA TBD（8 项）分开两节，避免混淆
4. **唯一日语艺人 ≠ 必须做日语专属**：7 艺人作背景音乐上下文里，A4 仅占一个独立算法池，跨语种联名（A3+A4）是隐性资产
