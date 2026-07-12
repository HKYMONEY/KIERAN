---
status: locked
topic: hermes-evolution
artist: weini
scope: 微霓项目专用 (后续克隆到其他艺人)
created: 2026-07-11
updated: 2026-07-11
related:
  - 微霓项目指南 v0.2 (2026-07-11)
  - multi-artist-label-playbook SKILL.md v4.7
  - haevo-a-r-control-table SKILL.md
  - kieran-obsidian-git-sync SKILL.md
tags: [hermes-cos, weini, artist-os, knowledge-maturity, brand-dna]
---

# Hermes v2.0 微霓项目模式 — 提升规划 + 日程表

**定位**: Hermes 不是 "AI 助手" — 是 **Haevo Records Creative Operating System (COS)** 的微霓项目实例
**核心哲学**: Observe → Hypothesis → Experiment → Measure → Update 闭环 + 知识成熟度 L1-L4
**范围**: 本文档 = 微霓项目专用, 后续克隆到其他 7 艺人

---

## 0. 修订日志

| 版本 | 日期 | 修订 | 来源 |
|---|---|---|---|
| v0.1 | 2026-07-11 | 8 模块 + 5 能力树 + 4 级知识成熟度 + Daily/Weekly/Monthly/Quarterly 调度框架 | Kieran 2026-07-11 |

---

## 1. 8 个长期成长模块 (微霓项目实例)

### 模块 ① Lyrics Lab (歌词实验室) ⭐⭐⭐⭐⭐

**目标**: 不是存最终歌词, 而是建立 **情绪 → 意象 → 句子 → 段落 → 歌词** 五层累积

| 层 | 内容 | 存储格式 | 频率 |
|---|---|---|---|
| L1 情绪 | 等待 / 空窗 / 未完成 / 告别 / 成长 | YAML key-value | Daily |
| L2 意象 | 月 / 窗 / 雨 / 灯 / 影子 / 玻璃 / 海 | tag array | Daily |
| L3 句子 | 完整歌词候选句 | .md 单文件 | Daily (≥ 10 句/日) |
| L4 段落 | 8 段结构完整歌词 | .md (≥ 400 char) | Weekly (≥ 3 段/周) |
| L5 歌词 | 已发布 Track 终版 | .md (LOCKED) | Track 发行时 |

**KPI**: 一年后 ≥ 3000 句歌词素材, ≥ 100 段 8 段结构歌词
**Knowledge Maturity**: L3 → L4 (经 Track 验证后才升 L4)

### 模块 ② Mood Library (情绪库)

**原则**: 不按"快乐/悲伤"分类, 按**现代人真实情境**分类

| 类别 | 情境词 | 用途 |
|---|---|---|
| 时间 | 睡前 / 通勤 / 凌晨 3 点 / 失眠 / 周末下午 | 歌词场景锚点 |
| 天气 | 下雨 / 雪 / 黄昏 / 蓝调时刻 / 微光 | 意象对应 |
| 关系 | 异地恋 / 独居 / 毕业 / 告别 / 失联 | 情感主题 |
| 状态 | 社恐 / 放空 / 冥想 / 治愈 / 疲惫 | 听歌情境 |
| 空间 | 地铁 / 机场 / 城市夜 / 山路 / 河岸 | 视觉+编曲双锚 |

**KPI**: 100+ 情境词, 每个词对应 ≥ 3 个意象 + ≥ 5 句候选歌词
**Knowledge Maturity**: L2 → L3 (经 Track 数据验证)

### 模块 ③ Trend Radar (社会情绪雷达)

**原则**: 不是追热点, 是观察"为什么哭 / 为什么焦虑 / 为什么收藏"

**数据源 (按频率)**:

| 源 | 频率 | 抓取内容 |
|---|---|---|
| Reddit r/music / r/ambient / r/chillhop | Daily 10 帖 | 评论关键词 + 高赞 |
| Spotify Editorial 每周更新 | Weekly | 新歌单 + Playlist 描述 |
| TikTok Sounds 趋势 | Daily Top 20 | BGM 用法 + 视频配文 |
| 小红书音乐话题 | Daily | 笔记情绪标签 |
| 微博热搜音乐 | Daily | 话题讨论度 |
| YouTube Trending Music | Daily | 视频评论高频词 |

**输出**: Market Emotion Report (Daily 1 页, 提炼"今年越来越多人...")
- 例: 2026 趋势主线 = 怀念 2000 / 喜欢安静 / 逃离内卷 / Forest / Slow Living / Night Walk / Late Summer

**KPI**: 每周 1 份 Market Emotion Report (≥ 3 个趋势主线)
**Knowledge Maturity**: L2 (默认待验证) → L3 (经 Track 验证)

### 模块 ④ Artist DNA Evolution

**原则**: 每首歌发行后录入, 一年后知道"哪些真属于微霓"

**录入字段** (Track 发行 +1 日内):

| 字段 | 类型 | 示例 |
|---|---|---|
| Title | string | 长安月 |
| Genre | enum | Ambient Pop |
| Subgenre | enum[] | Dream Pop / Guofeng |
| Prompt | text | (Suno Style of Music 完整) |
| Lyrics | text | (8 段结构完整) |
| BPM | int | 74 |
| Key | enum | D minor |
| Cover URL | string | (3000x3000) |
| Mood Tags | string[] | [留白, 月, 思念] |
| Why Worked | text | (Track 验证后填写) |
| Why Failed | text | (Track 验证后填写) |

**分析维度** (Monthly):
- DNA Drift (Track N 跟 Brand DNA 距离)
- DNA Health Score (0-10, 综合 Save rate + 评论关键词 + 完成率)

**KPI**: 5 首 Track 后首份 DNA Drift 报告
**Knowledge Maturity**: L4 (Track 数据是 ground truth)

### 模块 ⑤ Prompt Research Lab

**原则**: Suno 输出不浪费, 全录入形成 Prompt Library

**录入字段**:

| 字段 | 类型 | 示例 |
|---|---|---|
| Prompt | text | Chinese dream pop, ambient, ... |
| Genre | enum | Dream Pop |
| Key | enum | D minor |
| Tempo | int | 74 |
| Voice | enum | Female whisper |
| Quality Score | float (0-10) | 9.2 |
| Human Notes | text | "人声很好, 副歌太弱" |

**分析维度** (Monthly):
- Prompt 排行 (Top 10 稳定 Prompt)
- Prompt 退役 (Score < 7.0 持续 3 月)
- Prompt 进化 (新发现的高分 Prompt)

**KPI**: 50+ Prompt 录入, Top 10 锁定 (Score ≥ 8.5)
**Knowledge Maturity**: L3 (≥ 3 次验证) → L4 (≥ 6 月稳定)

### 模块 ⑥ Reference Music Library

**原则**: 不收藏喜欢的歌, 是拆解

**拆解字段** (每首 Reference):

| 字段 | 内容 |
|---|---|
| Title / Artist | 夜曲 / 周杰伦 |
| Intro | (前 8s 描述: 钢琴 + 弦乐) |
| Verse | (V1 编曲 + vocal 处理) |
| Pre-Chorus | (张力构建) |
| Chorus | (Hook 抓耳原因) |
| Bridge | (转折技巧) |
| Outro | (收尾方式) |
| Why收藏率高 | (评论 + 数据综合) |
| Why副歌抓耳 | (旋律 + 编曲 + vocal 角度) |

**KPI**: 30+ Reference 拆解 (按流派分: Mandopop 10 / Ambient Pop 10 / Dream Pop 10)
**Knowledge Maturity**: L2 (默认) → L3 (经 Track 模仿验证)

### 模块 ⑦ Visual DNA Library

**原则**: 所有封面 / Canvas / 视频打标签

**标签体系**:

| 维度 | 标签 |
|---|---|
| 元素 | 月 / 窗 / 雨 / 灯 / 影子 / 玻璃 / 海 / 山 |
| 地点 | 东京 / 北京 / 台北 / 巴黎 / 海岸 / 山路 |
| 摄影 | 长焦 / 浅景深 / 胶片颗粒 / 雾化光 / 柔焦 / 电影感 |
| 色温 | 3200K / Blue Hour / Fog / Bokeh / Minimal |
| 构图 | 居中 / 三分 / 对称 / 框中框 |
| 情绪 | 静 / 梦 / 思念 / 留白 / 夜 / 孤独 / 希望 |

**KPI**: 50+ 视觉资产标签化, AI 直接知道"微霓长什么样"
**Knowledge Maturity**: L3 (经 Track 封面验证)

### 模块 ⑧ Audience Memory (听众记忆库) ⭐ 最重要

**原则**: 不只录数据, 录评论

**录入字段** (每 Track 发行 +7/+30/+90 日):

| 平台 | 评论原文 | 情绪关键词 | 场景关键词 |
|---|---|---|---|
| Spotify | "凌晨听哭了" | 思念 / 孤独 | 凌晨 |
| YouTube | "像东京下雨" | 治愈 | 雨天 |
| Apple Music | "适合夜晚" | 静 | 夜 |
| Instagram | "这首歌让我想到奶奶" | 思念 / 回忆 | — |
| 小红书 | "通勤单曲循环" | 陪伴 | 通勤 |

**分析维度** (Monthly):
- 评论关键词云
- 共鸣句排行 (Top 10 被打动最多)
- 场景分布 (听众在什么场景听)

**KPI**: 100+ 评论录入, ≥ 10 共鸣句识别
**Knowledge Maturity**: L4 (听众反馈是 ground truth)

### 模块 ⑨ Artist Philosophy (隐藏模块, 长期最重要)

**三问恒定**:

| 问 | 答案 |
|---|---|
| **为什么唱** | 不是表达自己, 是替那些说不出口的人唱 |
| **为什么存在** | 让东方情绪以现代音乐继续流动 |
| **什么永远不会变** | 留白 / 真实 / 克制 / 安静 |

**用途**: 每年 Track 决策时, 检查是否符合 Philosophy; 不符合 → 拒绝发布

**Knowledge Maturity**: L4 (永久)

---

## 2. 5 大能力树 (微霓实例归类)

```
Hermes 微霓项目模式
├── Market Intelligence (市场)
│   ├── ② Mood Library
│   └── ③ Trend Radar
│
├── Creative Intelligence (创作)
│   ├── ① Lyrics Lab ⭐
│   └── ⑥ Reference Music Library
│
├── Production Intelligence (制作)
│   ├── ⑤ Prompt Research Lab
│   └── 微霓项目指南 v0.2 (SOP 文档)
│
├── Knowledge Intelligence (知识)
│   ├── ⑦ Visual DNA Library
│   ├── ⑧ Audience Memory
│   └── Artist DNA Evolution (模块 ④)
│
└── Self Evolution (自我成长) ⭐ 最重要
    ├── ⑨ Artist Philosophy
    ├── 知识成熟度 L1-L4 系统
    ├── Confidence System (可信度)
    ├── Error Database (错误库)
    └── Experiment Framework (实验框架)
```

---

## 3. 4 级知识成熟度系统 (Knowledge Maturity)

| 等级 | 含义 | 是否进入 SOP | 例 |
|---|---|---|---|
| **L1** | 灵感 / 想法 | ❌ 不进入 | "Mandopop 可能用 Alternative 主曲风" |
| **L2** | 有行业案例支持 | ⚠️ 标记为待验证 | "Spotify Save Rate ≥ 3% 是 Mandopop 健康线" (引用 Revelator) |
| **L3** | 经 Haevo 自己多次验证 | ✅ 可进入工作流 | "微霓 74 BPM Track 1 Save Rate 4.2%" |
| **L4** | 长期稳定, 反复验证 | ✅ 进入核心标准 | "微霓 Track 1-5 全部 72-78 BPM + 5 minor Key 池" |

**升级规则**:
- L1 → L2: 找到 ≥ 2 个独立行业引用
- L2 → L3: 微霓自有 Track ≥ 2 次验证
- L3 → L4: ≥ 6 月稳定 + ≥ 5 Track 验证

**降级规则**:
- L4 → L3: 1 次 Track 失败
- L3 → L2: 2 次连续 Track 失败
- L2 → L1: 行业引用过期 / 反驳

---

## 4. Confidence System (可信度系统)

每条知识带 **可信度星级**:

| 来源 | 默认星级 | 备注 |
|---|---|---|
| Spotify / Apple Music / RouteNote 官方 | ★★★★★ | 官方数据 |
| Soundcharts / LANDR / DistroMono 行业报告 | ★★★★☆ | 引用源 |
| Revelator / Playlist Pilot / LANDR blog | ★★★☆☆ | 媒体观点 |
| Hermes 实验 (100+ 首歌数据) | ★★★★☆ | 自有数据 |
| Reddit / Twitter / 小红书 有人说 | ★★☆☆☆ | 单点观察, 需多源验证 |

**规则**: L4 SOP 必须 ≥ ★★★★ 来源

---

## 5. 每日固定任务 (Daily Loop)

| 时间 (CST) | 任务 | 模块 | 输出 |
|---|---|---|---|
| 08:00 | ① Lyrics Lab 训练 | ① Lyrics Lab | 1 个意象 → 10 句候选 |
| 08:30 | ③ Trend Radar 扫描 | ③ Trend Radar | Daily Market Emotion 摘要 |
| 09:00 | ⑤ Prompt Research Lab 检查 | ⑤ Prompt Lab | Suno 新输出录入 |
| 09:30 | ⑧ Audience Memory 录入 | ⑧ Audience Memory | 评论录入 (如 Track 已发) |
| 20:00 | Daily Recap | All | 推送 Telegram 1 条 |

**Telegram Morning Brief 模板** (Daily 20:00 推送):

```
🌅 Hermes Daily Brief — 微霓项目
日期: 2026-07-12

📊 Market Emotion: [1-2 句]
🎨 Lyrics Lab: 今日意象 [X] → 10 句候选已录入
🎵 Prompt: [新发现 / 退役 / 排行变化]
📝 Track 状态: [Track 2 SOP 进度]
💡 今日建议: [1 句可执行建议]

参考: [1-2 个数据源链接]
```

---

## 6. 每周固定任务 (Weekly Review)

**时间**: 周日 21:00 CST

| 任务 | 模块 | 输出 |
|---|---|---|
| Weekly Lyrics 汇总 | ① Lyrics Lab | 本周 70 句 Top 10 + 1 段 8 段结构完整歌词 |
| Market Emotion Report | ② + ③ | 1 页报告 (3 个趋势主线 + 听众情绪) |
| Prompt 排行 | ⑤ | Top 5 稳定 Prompt + 退役 1-2 个 |
| Reference 拆解 | ⑥ | 1-2 首 Reference 新拆解 |
| Visual 一致性检查 | ⑦ | 本周新封面 vs Brand DNA 距离 |
| 评论关键词云 | ⑧ | Top 20 关键词 + 3 个共鸣句 |
| Philosophy vs 实际校准 | ⑨ | 本周 Track 是否符合 Philosophy |

**输出**: `weekly-review-YYYY-MM-DD.md` 推 Obsidian + Telegram 摘要

---

## 7. 每月固定任务 (Monthly Evolution)

**时间**: 每月最后一天 21:00 CST

| 任务 | 输出 |
|---|---|
| DNA Drift 检查 | ④ Artist DNA Health Score 0-10 + drift 距离 |
| Prompt 进化 | ⑤ Top 10 锁定 + 3-5 个退役 |
| Visual 资产月度 Top | ⑦ 高频元素 + 色板 + 构图 |
| Audience 情绪曲线 | ⑧ 月度情绪关键词变化 |
| Philosophy 刷新 | ⑨ 季度核心哲学微调 |

**输出**: `monthly-evolution-YYYY-MM.md` 推 Obsidian + Telegram 摘要

---

## 8. 每季度固定任务 (Quarterly Re-evaluation)

**时间**: 每季度末

| 任务 | 输出 |
|---|---|
| 艺人重评 (微霓 → 其他 7 艺人克隆) | 各艺人 Health Score 对比 |
| Error Database 更新 | 本季度新错误 + 防止措施 |
| Experiment Framework 立项 | 下季度 1-2 个 A/B 实验 |
| Knowledge Maturity 升级 / 降级 | L4 核心 SOP 更新 |

**输出**: `quarterly-review-YYYY-QX.md` 推 Obsidian + Telegram 摘要

---

## 9. Experiment Framework (实验框架)

**结构**:

```
Experiment #XXX
Question: [可证伪假设]
Method: [A/B 设计]
Variables Controlled: [固定变量]
Variables Varied: [变化变量]
Duration: [时长]
Measure: [Save Rate / Completion / Comments 关键词]
Pass: [判定标准]
Fail: [回滚策略]
```

**微霓项目第一个实验候选**:

| # | Question | Method | Measure |
|---|---|---|---|
| #001 | 74 BPM vs 78 BPM 在 Brand Establishment 阶段哪个 Save Rate 更高? | Track 2 (74) vs Track 3 (78), 其他变量固定 | Save Rate @ D+30 |
| #002 | 月 vs 窗 哪个意象评论共鸣更高? | Track 4 (月) vs Track 5 (窗) | 评论关键词 "月" vs "窗" 频次 |
| #003 | Negative Prompt 8 行 vs 4 行 哪个 Suno 命中率高? | Track 6 (8 行) vs Track 7 (4 行), 跑 4 段 | 结构服从率 + vocal 清晰度 |

---

## 10. Error Database (错误库)

**录入字段**:

| 字段 | 例 |
|---|---|
| Mistake | Track 1 Genre 误选 "Alternative" 主 |
| Why Failed | RouteNote 表单 dropdown 不含 Alternative (Mandopop Editorial 入口断) |
| When | 2026-07-01 RouteNote 表单实测 |
| How to Prevent | 未来 Track Genre 先用 `multi-artist-metadata-automation/scripts/validate_genre.py` fail-closed 验证 |
| Knowledge Maturity Impact | L3 → L4 (RouteNote 39-list 永久锁定) |

**第一个录入** (本规划生成的同时间):

| Mistake | Why Failed | Prevent |
|---|---|---|
| Track 1 长安月 Genre 用 "Alternative" 主曲风 | RouteNote dropdown 不接受 → 算法路由断 | 验证脚本 + 双 Genre 备选 (Pop / World) |
| Suno 168 char Lyric 不服从 8 段结构 | Lyrics 字段被当 inspiration 处理 | ≥ 400 char + 8 段 + 显式 Bridge / Instrumental Break |
| 单跑 2 段验证浪费 1 轮 | Suno 默认 4 段才能判断服从率 | Domain 3 直接跑 4-8 段 |

---

## 11. 调度实施 (VPS cron)

**前提**: 需要 Kieran 授权创建 cron (bot-b profile 默认 cron 未启用)

**Cron 计划表** (建议):

```bash
# Daily 20:00 CST = 12:00 UTC
0 12 * * * /usr/bin/python3 /var/codex_project/hermes-home/profiles/bot-b/scripts/hermes-daily.py --artist weini

# Weekly Sunday 21:00 CST = 13:00 UTC
0 13 * * 0 /usr/bin/python3 /var/codex_project/hermes-home/profiles/bot-b/scripts/hermes-weekly.py --artist weini

# Monthly last day 21:00 CST = 13:00 UTC
0 13 28-31 * * /usr/bin/python3 /var/codex_project/hermes-home/profiles/bot-b/scripts/hermes-monthly.py --artist weini

# Quarterly last day 21:00 CST = 13:00 UTC
0 13 30 3,6,9,12 * /usr/bin/python3 /var/codex_project/hermes-home/profiles/bot-b/scripts/hermes-quarterly.py --artist weini
```

**脚本占位**: `hermes-daily.py` / `weekly.py` / `monthly.py` / `quarterly.py` 待创建

---

## 12. 实施路线图 (3 阶段)

### Phase 1: 基础搭建 (T-56 ~ T-49, 2026-07-11 ~ 2026-07-24)
- ✅ 文档就位 (本文件 + 微霓项目指南 v0.2)
- [ ] 创建 VPS 目录结构 `weini-cos/{lyrics,mood,trend,dna,prompt,reference,visual,audience,philosophy}/`
- [ ] 4 个 cron 脚本占位 (`hermes-{daily,weekly,monthly,quarterly}.py`)
- [ ] Kieran 授权 cron 启用

### Phase 2: 启动运转 (T-42 ~ T-14, 2026-07-25 ~ 2026-08-28)
- Daily Loop 启动 (Lyrics Lab 每日 10 句 + Trend Radar 每日扫描)
- Weekly Review 启动 (周日汇总)
- Track 2 SOP 与 COS 同步推进 (Domain 1-7 嵌入 COS 录入点)

### Phase 3: 成熟运营 (Track 2 发行后, 2026-09-11+)
- Monthly Evolution 启动
- Error Database 累积
- Experiment Framework 启动 (#001 #002 #003)
- 克隆 COS 到其他 7 艺人 (Lune Veya / Rowan Vale / Veloria Senda / Shibata Luna / Oaeli / Aube Valois)

---

## 13. 待解决问题 (本版本需 Kieran 决策)

1. **Cron 授权**: 是否授权 bot-b 创建 4 个 cron (daily/weekly/monthly/quarterly)?
2. **VPS 资源**: 每日 Trend Radar 扫描 Reddit/Spotify/TikTok/小红书 需要 API key, 是否接受配置?
3. **Maturity 起点**: 微霓项目指南 v0.2 的所有锁定值, 默认 Knowledge Maturity = L3 还是 L2?
4. **Phase 1 优先级**: 创建目录结构 + cron 脚本占位, 是否本周内完成?
5. **Lyrics Lab 训练数据源**: 每日 10 句中文歌词训练, 数据源是 (a) Kieran 提供种子词 / (b) Hermes 自主从 Trend Radar 抓意象 / (c) 混合?
6. **品牌资产克隆范围**: 未来克隆到其他艺人, 是 (a) 整套 9 模块克隆 / (b) 仅核心 5 模块 (Lyrics Lab / Prompt Lab / Visual DNA / Audience Memory / Philosophy) 克隆?
7. **Experiment Framework #001-003 启动时间**: 是否 Track 2 发行后立刻启动, 还是再等 2-3 Track 数据?

---

## 14. 引用

- Kieran 2026-07-11 Hermes v2.0 设计哲学 (8 模块 + 5 能力树 + 4 级知识成熟度)
- 微霓项目指南 v0.2 (2026-07-11)
- multi-artist-label-playbook SKILL.md v4.7 (5 艺人 + 24h 闭环)
- haevo-a-r-control-table SKILL.md (Domain 3 7 维度)
- haevo-aube-qc-framework (TP -1.2 / 44.1kHz / K-weighting 算法)
- kieran-obsidian-git-sync SKILL.md (Obsidian ↔ VPS 链路)
- suno-5.5-ambient-workflow SKILL.md (Whisper multi-window 评估)
- Spotify Editorial 已验证 Playlist (Deep Focus / Ambient Relaxation)

---

⚠️ **[v0.1 LOCKED 草案, 待 Kieran 7 项决策拍板]**

📋 **7 项决策 (按优先级排序)**:

1. 🔥 **Cron 授权**: 是否同意 bot-b 创建 4 个 cron (daily/weekly/monthly/quarterly)?
2. 🔥 **API key 准备**: 是否接受 Trend Radar 需要 Reddit/Spotify/TikTok/小红书 API 配置?
3. **Maturity 起点**: v0.2 所有锁定值默认 L3 (可工作流) 还是 L2 (待验证)?
4. **Phase 1 启动**: 本周内创建 `weini-cos/` 目录 + cron 脚本占位?
5. **Lyrics Lab 数据源**: Kieran 提供 / Hermes 自抓 / 混合?
6. **品牌资产克隆范围**: 9 模块全套 / 5 模块核心?
7. **Experiment 启动**: Track 2 发行后立刻 / 再等 2-3 Track?