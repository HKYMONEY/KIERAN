---
resource_type: FLAC Tag 标准化模板 (Haevo Records 厂牌级 SOP)
project: haevo-records
applicable_to: 所有 8 名艺人母带 FLAC 文件
version: v1.0
status: LOCKED (Permanent Rule, Slow Evolution)
last_updated: 2026-07-11
confidence: ★★★★ (Spotify/Apple/YouTube 平台通用 + 1 Track 实战 + 8 艺人 SOP 框架)
next_review: 2026-10-11 (季度 Review)
---

# Haevo Records — 8 艺人 FLAC Tag 标准化模板 v1.0

> **目的**: 为 Haevo Records 旗下 **8 名艺人**的所有 Track 母带 FLAC 文件提供**统一、可执行、可脚本化**的 Tag 标准化模板。本文件 = 厂牌级 SOP, **歌曲名字段留空** (等具体 Track 锁定后填), **8 艺人信息单独表** (见 § 3)。

---

## 0. 使用方式

### 0.1 何时填 tags?
- **D4 母带锁定后** (Playbook D4 节点)
- **D6 平台提交前** (Playbook D6 节点, 最终把关)

### 0.2 怎么填?
- **手动**: `metaflac --set TAG=VALUE` 逐条写
- **脚本自动化**: `apply-flac-tags.py <file.flac> --artist <id> --track <name> --isrc XX --upc XX` (待创建)

### 0.3 8 艺人 ID 速查 (官方映射, 来自 `八位藝人流量權重曲風映射報告.md`)

> **Genre 全 RouteNote v4.2 39-list 合法映射**, Subgenre 自由填入用于精准路由
> **流量权重**: 2 高成长 (#8, #44-47) + 3 亚洲核心 (#29-33) + 3 长尾功能 (#29-50)

| ID | 中文名 | 英文名 | 主要语言 | 主 Genre | 副 Genre | Subgenre | 流量权重 |
|---|---|---|---|---|---|---|---|
| A1 | Rowen Vale | Rowen Vale | en | Alternative | Singer/Songwriter | Folk Pop;Indie Folk;Singer-Songwriter | **#8 Indie Rock** (高成长) |
| A2 | Lune Veya | Lune Veya | en | Pop | Alternative | Dark Pop;Bedroom Pop | **#31 Bedroom Pop** |
| A3 | 微霓 (薇婭) | Weini | zh-Hant + zh-Hans | Pop | World | Mandopop;華語流行;Taiwanese Pop | **#29 Mandopop** |
| A4 | Shibata Luna | Shibata Luna | ja + en | J-Pop | Pop | City Pop;J-Pop | **#33 City Pop** |
| A5 | Haevo | Haevo | en + instrumental | Electronic | Alternative | Ambient;Dark Ambient;Lofi Ambient;Drone | **#50 Ambient Electronic** |
| A6 | Oaeli | Oaeli | es + en | Latin | Alternative | Latin Pop;Spanish Pop | **#44 Latin Pop** |
| A7 | Aube Valois | Aube Valois | fr + en | Pop | - | French Chanson;Chanson Française | **#29-35 Pop 类** |
| A8 | Veloria Senda | Veloria Senda | es + en | Latin | World | Latin Folk;World Music | **#44-47 Latin 类** |

> **原始资料**: `八位藝人流量權重曲風映射報告.md` (HKYOB 根目录, v2.0 / 2026-07-10)
> **发行优先级**: 🥇 P0 = Rowen Vale + Weini / 🥈 P1 = Veloria Senda + Lune Veya + Shibata Luna / 🥉 P2 = Oaeli + Aube Valois + Haevo

---

## 1. 必备 Tag 清单 (28 项, 厂牌级强制)

> **通用规则**:
> - **歌曲名 / 歌词 / 描述 / Track 号**: **本模板留空, 等具体 Track 锁定后填**
> - **艺人 / 厂牌 / 语言 / Genre / ISRC / UPC**: 从 § 3 艺人表 + 平台 dashboard 自动填
> - **AI 声明**: Haevo Records 厂牌政策强制填

| # | Tag 名 | 必填 | 值规则 | 示例 (A1 微霓 Track 02) |
|---|---|---|---|---|
| 1 | TITLE | ✅ | `{Track 中文名}` (主语言) | `窗與燈` |
| 2 | ARTIST | ✅ | `{中文名} ({英文名})` | `微霓 (Weini)` |
| 3 | ALBUM | ✅ | `{Track 中文名}` (单曲专辑名同 Track) | `窗與燈 (Single)` |
| 4 | ALBUMARTIST | ✅ | `{中文名} ({英文名})` | `微霓 (Weini)` |
| 5 | TRACKNUMBER | ✅ | `{N}` (Track 在 Album 序号) | `1` |
| 6 | TRACKTOTAL | ✅ | `{Total}` (Album 总 Track 数) | `1` (单曲) |
| 7 | GENRE | ✅ | RouteNote 39-list **主 Genre** | `Pop` |
| 8 | SUBGENRE | ⚠️ 推荐 | `;` 分隔 Sub-tag (Brand DNA, **以官方映射为准**) | `Mandopop;華語流行;Taiwanese Pop` |
| 9 | LANGUAGE | ✅ | IETF 主语言代码 | `zh-Hant` |
| 10 | LANGUAGE_SECONDARY | ⚠️ 推荐 | IETF 副语言代码 | `zh-Hans` |
| 11 | LYRICS | ⚠️ 推荐 | 完整歌词 (主语言) | `{Lyrics v0.3-zhHant 内容}` |
| 12 | LYRICS_SECONDARY | ⚠️ 可选 | 完整歌词 (副语言) | `{Lyrics v0.3-zhHans 内容}` |
| 13 | DATE | ✅ | Release Date YYYY-MM-DD | `2026-09-11` |
| 14 | YEAR | ✅ | Release Year YYYY | `2026` |
| 15 | ORIGINALRELEASEDATE | ⚠️ 推荐 | 同 DATE | `2026-09-11` |
| 16 | COMPOSER | ✅ | 作曲者全名 (Haevo 用英文) | `XIAOYANG ZHANG` |
| 17 | LYRICIST | ✅ | 作词者全名 | `XIAOYANG ZHANG` |
| 18 | PRODUCER | ✅ | 制作人全名 | `XIAOYANG ZHANG` |
| 19 | LABEL | ✅ | 厂牌标准名 | `Haevo Records` |
| 20 | PUBLISHER | ⚠️ 推荐 | 发行商 | `Haevo Records` |
| 21 | CATALOGNUMBER | ⚠️ 可选 | 厂牌内部编号 | `HR-A1-T02` |
| 22 | ISRC | ✅ | 12 字符 (RouteNote 自动) | `GXFHP2653163` |
| 23 | UPC | ⚠️ 推荐 | 13 位 EAN-13 (单曲可空) | `5064041048082` |
| 24 | BARCODE | ⚠️ 可选 | 同 UPC | `5064041048082` |
| 25 | AI_DISCLOSURE | ✅ (Haevo 政策) | AI 生成声明 | `AI-generated music under Haevo Project` |
| 26 | COPYRIGHT | ✅ | `© {YEAR} {Label}` | `© 2026 Haevo Records` |
| 27 | ENCODEDBY | ⚠️ 可选 | 编码工具版本 | `Lavf60.16.100` |
| 28 | REPLAYGAIN_* | ⚠️ 可选 | 响度归一化 | (loudnorm 自动) |

### 1.1 Tag 缩写对照 (metaflac 命令格式)

| 完整名 | metaflac 缩写 |
|---|---|
| TITLE | TITLE |
| ARTIST | ARTIST |
| ALBUM | ALBUM |
| ALBUMARTIST | ALBUMARTIST |
| TRACKNUMBER | TRACKNUMBER |
| TRACKTOTAL | TRACKTOTAL |
| GENRE | GENRE |
| SUBGENRE | 不在标准, 用 `; ` 分隔写进 GENRE 或自定义 |
| LANGUAGE | 不在标准, 用自定义 tag `LANGUAGE` |
| LYRICS | 不在标准, 用自定义 tag `LYRICS` |
| DATE | DATE |
| YEAR | DATE (只取年份部分) |
| COMPOSER | COMPOSER |
| LYRICIST | LYRICIST |
| PRODUCER | PRODUCER |
| LABEL | ORGANIZATION (标准) 或 LABEL (自定义) |
| ISRC | ISRC |
| UPC | BARCODE |
| COPYRIGHT | COPYRIGHT |
| ENCODEDBY | ENCODED-BY |

> **注意**: 部分 tag 不是 FLAC/Vorbis 标准 (SUBGENRE / LANGUAGE / LYRICS / AI_DISCLOSURE), 但 metaflac 支持自定义 tag。Spotify/Apple/YouTube 会读自定义 tag 但**优先级低于标准 tag**。

---

## 2. 母带文件结构 (FLAC + Cover)

### 2.1 必备结构

```
{Track-中文名}-{Artist-ID}-mastered.flac
├── Stream 0: Audio (FLAC, 44.1kHz, 16bit, 1ch OR 2ch)
├── Stream 1: Cover (PNG, 3000x3000, attached pic)
├── METADATA block 0: STREAMINFO (含内嵌 MD5)
├── METADATA block 1: VORBIS_COMMENT (含上面 28 项)
└── METADATA block 2: PICTURE (1 张 3000x3000)
```

### 2.2 文件命名规范

```
{Track-中文名}-{Artist-ID}-mastered.flac
例: 窗與燈-A1-mastered.flac
例: {TBD}-A2-mastered.flac (Aube Valois Track 1)
```

**规则**:
- 中文名: 主语言 (繁主简副 / 简主繁副, 按艺人)
- Artist ID: A1-A8
- `-mastered` 后缀: 表示这是 D4 母带 (非原始 Suno 输出)
- `.flac`: FLAC 格式
- 路径: `10-Projects/{Project}/delivery/T{NN}/{filename}`

### 2.3 Cover 要求

| 项 | 标准 |
|---|---|
| 分辨率 | **3000 x 3000 px** (Spotify 最低 3000) |
| 格式 | PNG (无损) 或 JPG (高质量 ≥ 95%) |
| 大小 | ≤ 20 MB (PICTURE block 上限) |
| 内容 | 符合 Artist Brand DNA § 5 (Visual SOP) |
| 命名 | `cover-3000.png` (默认) 或 `{Artist-ID}-cover.png` |

---

## 3. 8 艺人 Profile 表 (Haevo Records 标准)

> **本表是厂牌级 SOP**, 歌曲名 / Track 编号 / 歌词 等 Track 特有字段**留空, 等具体 Track 锁定后填**。
> **数据来源**: `八位藝人流量權重曲風映射報告.md` (HKYOB 根目录, v2.0 / 2026-07-10, 官方映射)
> **Genre 全 RouteNote v4.2 39-list 合法映射**

### A1 — Rowen Vale (Indie Folk / Folk Pop) 🥇 P0

| 字段 | 值 |
|---|---|
| 中文名 | (无中文名, 英文) |
| 英文名 | Rowen Vale |
| ARTIST tag | `Rowen Vale` |
| 主要语言 | en |
| 主 Genre | Alternative |
| 副 Genre | Singer/Songwriter |
| Subgenre (RouteNote 自由填) | Folk Pop;Indie Folk;Singer-Songwriter |
| Top 50 流量权重 | **#8 Indie Rock** (高成长, Save Rate 高) |
| 目标市场 | 全球 (英美 Indie 受众) |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (Haevo 默认) |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A1-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 发行优先级 | 🥇 P0 |

### A2 — Lune Veya (Dark Pop / Bedroom Pop) 🥈 P1

| 字段 | 值 |
|---|---|
| 中文名 | (无中文名, 英文) |
| 英文名 | Lune Veya |
| ARTIST tag | `Lune Veya` |
| 主要语言 | en |
| 主 Genre | Pop |
| 副 Genre | Alternative |
| Subgenre | Dark Pop;Bedroom Pop |
| Top 50 流量权重 | **#31 Bedroom Pop** (影视配乐、Lo-fi 场景需求强) |
| 目标市场 | 全球 (Bedroom Pop 受众) |
| 转媒体潜力 | 高 (影视配乐需求强) |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (Haevo 默认) |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A2-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 发行优先级 | 🥈 P1 |

### A3 — 微霓 (Weini, 薇婭) (Mandopop) 🥇 P0 ✅ 已实战

| 字段 | 值 |
|---|---|
| 中文名 | 微霓 (薇婭) |
| 英文名 | Weini |
| ARTIST tag | `微霓 (Weini)` |
| 主要语言 | zh-Hant (主) + zh-Hans (副) |
| 主 Genre | Pop |
| 副 Genre | World |
| Subgenre (官方映射, 2026-07-11 v0.4 LOCKED) | **Mandopop;華語流行;Taiwanese Pop** |
| ~~Brand Bible v0.3 旧 Subgenre~~ | ~~`Chinese Folk;Mandopop;Alternative R&B`~~ (v0.4 已修正) |
| Top 50 流量权重 | **#29 Mandopop** (Spotify TW 算法推荐高) |
| 目标市场 | 台湾 + 中国大陆 + 东南亚 |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A3-T{NN}` |
| Brand Bible | `10-Projects/Music-RN-Research-2026/2026-07-11-Weini-Brand-Bible-v0.3.md` |
| 已发行 Track | T01 长安月 (实验轨), T02 窗與燈 (2026-09-11, In Review) |
| **Track 02 示例 FLAC** | `10-Projects/Music-RN-Research-2026/delivery/T02/窗與燈-A3-mastered.flac` |
| 发行优先级 | 🥇 P0 |

### A4 — Shibata Luna (City Pop / J-Pop) 🥈 P1

| 字段 | 值 |
|---|---|
| 中文名 | (无中文名) |
| 英文名 | Shibata Luna |
| ARTIST tag | `Shibata Luna` |
| 主要语言 | ja (主) + en (副) |
| 主 Genre | J-Pop |
| 副 Genre | Pop |
| Subgenre | City Pop;J-Pop |
| Top 50 流量权重 | **#33 City Pop** (Spotify JP/TW 流量稳定) |
| 目标市场 | 日本 + 全球 J-Pop |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (Haevo 默认) |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A4-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 发行优先级 | 🥈 P1 |

### A5 — Haevo (Ambient / Ambient Electronic) 🥉 P2

| 字段 | 值 |
|---|---|
| 中文名 | Haevo (厂牌同名艺人) |
| 英文名 | Haevo |
| ARTIST tag | `Haevo` |
| 主要语言 | en + instrumental |
| 主 Genre | Electronic |
| 副 Genre | Alternative |
| Subgenre | Ambient;Dark Ambient;Lofi Ambient;Drone |
| Top 50 流量权重 | **#50 Ambient Electronic** (长尾稳定, 功能型场景需求强) |
| 目标市场 | 全球 Ambient / 功能型 (专注 / 睡眠 / 冥想) |
| 功能型场景 | 专注、睡眠、冥想 |
| 长尾收藏率 | 高 |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (Haevo 默认) |
| LABEL | Haevo Records (厂牌 = 艺人同名) |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A5-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 发行优先级 | 🥉 P2 (长尾稳定) |

### A6 — Oaeli (Spanish Ambient Pop / Latin) 🥉 P2

| 字段 | 值 |
|---|---|
| 中文名 | (无中文名) |
| 英文名 | Oaeli |
| ARTIST tag | `Oaeli` |
| 主要语言 | es (主) + en (副) |
| 主 Genre | Latin |
| 副 Genre | Alternative |
| Subgenre | Latin Pop;Spanish Pop |
| Top 50 流量权重 | **#44 Latin Pop** (西班牙 + 拉美 + 全球) |
| 目标市场 | 西班牙 + 拉美 + 全球 |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (Haevo 默认) |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A6-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 发行优先级 | 🥉 P2 |

### A7 — Aube Valois (French Chanson / Pop) 🥉 P2

| 字段 | 值 |
|---|---|
| 中文名 | Aube (欧贝) — 待 Kieran 确认 |
| 英文名 | Aube Valois |
| ARTIST tag | `Aube Valois` |
| 主要语言 | fr (主) + en (副) |
| 主 Genre | Pop |
| 副 Genre | - (无副 Genre) |
| Subgenre | French Chanson;Chanson Française |
| Top 50 流量权重 | **#29-35 Pop 类** (法语区 + 欧洲 + 中文抒情跨域) |
| 目标市场 | 法语区 + 欧洲 |
| 跨域潜力 | 法语市场 + 中文抒情跨域, 触及欧亚听众 |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (待确认是否同一人) |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A7-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 已发行 Track | T01 (2026-07-09 LOCKED, 4:30 ambient) |
| **QC 标准** | `suno-5.5-ambient-workflow` skill (Aube v4 master pipeline 已验证) |
| 发行优先级 | 🥉 P2 |

### A8 — Veloria Senda (Latin Folk / World) 🥈 P1

| 字段 | 值 |
|---|---|
| 中文名 | (无中文名) |
| 英文名 | Veloria Senda |
| ARTIST tag | `Veloria Senda` |
| 主要语言 | es (主) + en (副) |
| 主 Genre | Latin |
| 副 Genre | World |
| Subgenre | Latin Folk;World Music |
| Top 50 流量权重 | **#44-47 Latin 类** (拉美 + 全球) |
| 目标市场 | 拉丁美洲 + 全球 |
| COMPOSER / LYRICIST / PRODUCER | XIAOYANG ZHANG (Haevo 默认) |
| LABEL | Haevo Records |
| AI_DISCLOSURE | AI-generated music under Haevo Project |
| Artist Profile URL (RouteNote) | TBD |
| Catalog Prefix | `HR-A8-T{NN}` |
| Brand Bible | TBD (建议创建) |
| 发行优先级 | 🥈 P1 |

---

## 4. metaflac 命令模板 (Copy-Paste 可用)

### 4.1 单文件批量设置 (示例: A3 微霓 Track 02)

```bash
FILE="窗與燈-A3-mastered.flac"

# 清空 tags (慎用, 会清除 PICTURE)
metaflac --remove-all-tags "$FILE"

# 必备 tags (28 项)
metaflac --set-tag="TITLE=窗與燈" \
         --set-tag="ARTIST=微霓 (Weini)" \
         --set-tag="ALBUM=窗與燈 (Single)" \
         --set-tag="ALBUMARTIST=微霓 (Weini)" \
         --set-tag="TRACKNUMBER=1" \
         --set-tag="TRACKTOTAL=1" \
         --set-tag="GENRE=Pop" \
         --set-tag="LANGUAGE=zh-Hant" \
         --set-tag="LANGUAGE_SECONDARY=zh-Hans" \
         --set-tag="DATE=2026-09-11" \
         --set-tag="YEAR=2026" \
         --set-tag="COMPOSER=XIAOYANG ZHANG" \
         --set-tag="LYRICIST=XIAOYANG ZHANG" \
         --set-tag="PRODUCER=XIAOYANG ZHANG" \
         --set-tag="LABEL=Haevo Records" \
         --set-tag="PUBLISHER=Haevo Records" \
         --set-tag="CATALOGNUMBER=HR-A3-T02" \
         --set-tag="ISRC=GXFHP2653163" \
         --set-tag="UPC=5064041048082" \
         --set-tag="AI_DISCLOSURE=AI-generated music under Haevo Project" \
         --set-tag="COPYRIGHT=© 2026 Haevo Records" \
         "$FILE"

# 自定义 tag (LYRICS / SUBGENRE)
metaflac --set-tag="LYRICS=完整 8 段繁体歌词..." \
         --set-tag="SUBGENRE=Mandopop;華語流行;Taiwanese Pop" \
         "$FILE"

# Cover (3000x3000 PNG)
metaflac --import-picture-from=cover-3000.png "$FILE"
```

### 4.2 验证 tags 写入正确

```bash
metaflac --list "$FILE" | head -80
```

---

## 5. 平台元数据 vs FLAC 文件元数据

### 5.1 双轨原则 (Haevo Records 强制)

| 元数据 | 在 FLAC 文件 | 在 平台 Dashboard (RouteNote/DistroKid) |
|---|---|---|
| TITLE | ✅ | ✅ |
| ARTIST | ✅ | ✅ |
| ALBUM | ✅ | ✅ |
| GENRE | ✅ | ✅ |
| LYRICS | ✅ | ✅ |
| LANGUAGE | ✅ | ✅ |
| DATE | ✅ | ✅ |
| ISRC | ✅ (自动分配后回填) | ✅ (平台分配) |
| UPC | ✅ (平台分配后回填) | ✅ (平台分配) |
| COVER | ✅ (PICTURE) | ✅ (平台再传 1 份) |
| AI_DISCLOSURE | ✅ | (平台不支持, 仅 FLAC 文件内) |
| CATALOGNUMBER | ✅ | (平台不支持, 仅厂牌内部) |

### 5.2 ⚠️ 已知问题 (Track 02 实测)

- **Spotify/Apple Music 优先读平台 dashboard 的 tags, 不读 FLAC 文件内嵌 tags**
- **Track 02 实测**: FLAC 文件仅 2 tags, 平台 dashboard 28 tags 完整 → In Review 正常推进
- **结论**: **必须双轨都填**, 不能只填 FLAC 文件

---

## 6. Track 制作 SOP 节点 (何时填 Tag)

| 节点 | 任务 | 填什么 |
|---|---|---|
| **D1 Suno Prompt** | 写 Prompt 草稿 | 不填 tag |
| **D2 Lyrics** | 锁定歌词 | 不填 tag (歌词单独存档) |
| **D3 Suno 试作** | 跑 A1-A4, 选 Best | 不填 tag |
| **D4 母带** | FLAC loudnorm + afade | **填 FLAC 文件 tags** (§ 1 清单) |
| **D5 封面** | 生成 Cover 3000x3000 | 不填 tag (Cover 单独存档) |
| **D6 RouteNote 提交** | 填平台 dashboard 表单 | **填平台 dashboard tags** (§ 5.1) |
| **D7 Pitch** | Spotify Editorial + Apple Music 预存 | 不填 tag |
| **T-0 上线** | 平台正式发布 | 不填 tag |

---

## 7. 引用

- [AUDIO-QC-STANDARD-v1.0.md](../../30-Resources/Audio-QC/AUDIO-QC-STANDARD-v1.0.md) — 母带 QC 8 大类 27 项 (55b08ef)
- [Brand Bible v0.3 — 微霓](../../10-Projects/Music-RN-Research-2026/2026-07-11-Weini-Brand-Bible-v0.3.md) — Artist DNA / Permanent 规则 (16 章)
- [Hermes v2.0 COS Plan v0.1](../../10-Projects/Music-RN-Research-2026/2026-07-11-Hermes-v2-Weini-COS-Plan-v0.1.md) — 8 艺人 COS 框架 (485 行)
- [DELIVERY-REPORT-v1.1](../../10-Projects/Music-RN-Research-2026/delivery/T02/DELIVERY-REPORT-v1.1.md) — Track 02 实战交付 (a570c50)
- [track-qc-check.py](https://github.com/HKYMONEY/KIERAN) — 自动化 QC 脚本 (bot-b/scripts)
- Spotify Master Guidelines: https://artists.spotify.com/
- Apple Music Master Guidelines: https://help.applemusic.com/
- metaflac 文档: https://xiph.org/flac/documentation_tools_metaflac.html

---

## 8. AI Update Log

| 日期 | 事件 |
|---|---|
| 2026-07-11 | v1.0 首版框架, 28 项必备 tags, A1+A2 已知 + A3-A8 待填 |
| 2026-07-11 | Track 02 实战验证: FLAC 文件 tags 2 条 (仅 encoder + Suno id), 平台 dashboard 28 条 tags 完整, In Review 正常推进 |
| 2026-07-11 | **v1.0 完整化**: 从 `八位藝人流量權重曲風映射報告.md` 读 8 艺人完整资料, § 0.3 + § 3 表全部填齐 (Rowen Vale / Lune Veya / Weini / Shibata Luna / Haevo / Oaeli / Aube Valois / Veloria Senda), 包含 Top 50 流量权重 + 发行优先级 + 目标市场 |
| 2026-07-11 | **v0.4 拍板**: Kieran 选 A. 以官方映射为准, Subgenre = `Mandopop;華語流行;Taiwanese Pop` (强调台湾 Mandopop 流 + Spotify TW 算法). Brand Bible v0.3 § 5 + Playbook v0.1 § 5 + DELIVERY-REPORT-v1.0 § 3 同步修正. 微霓 Subgenre 跨 4 文档一致 ✅ |
| 2026-Q4 (待) | 第一次季度 Review, 收集 5+ Track 数据后调 tags 列表 |

---

**标准版本**: v1.0 LOCKED
**下次 Review**: 2026-10-11 (季度)
**责任人**: bot-b (自动跑 QC + Tag 写入脚本) + Kieran (拍板 8 艺人 Brand DNA + 创建 7 个 Brand Bible)

**待办**:
1. ~~Kieran 拍板 Brand Bible v0.3 微霓 Subgenre 修正~~ ✅ DONE v0.4
2. 创建 7 个艺人 Brand Bible (A1/A2/A4/A5/A6/A7/A8, A3 微霓已有 v0.3, v0.4 Subgenre 修正)
3. 创建 `apply-flac-tags.py` 脚本 (参数化: --artist A1-A8 + --track + --isrc + --upc) ✅ DONE v1.0 (13.4KB)
4. 整理 `八位藝人流量權重曲風映射報告.md` 进 30-Resources/Artist-Profiles/ (现只在根目录)