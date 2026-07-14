<parameter name="content">---
title: US Market Radar 综合监控池 v3.0（去重整合版）
version: v3.0
status: LOCKED
created: 2026-07-14
updated: 2026-07-14
extends:
  - US-MARKET-SECTOR-UNIVERSE-v1.0-LOCKED.md
  - US-MARKET-SECTOR-UNIVERSE-v2.0-LOCKED.md
supersedes: none（v1.0 + v2.0 保留作历史 LOCKED 参考）
tags: [美股, Market Radar, v3, consolidated, locked]
data_source: yfinance + Yahoo Finance RSS + SEC EDGAR
report_cadence: weekly_only_Sat_21:00_CST
cron_job: f84a872bf4a9
---

# US Market Radar 综合监控池 v3.0

> **整合范围**：v1.0 列表（35 ETF + 100 代表股） + v2.0 架构（8 模块 + Sector Score + AI Overlay + Appendix）。
> **去重原则**：v1.0 / v2.0 都保留作历史归档；v3.0 是**唯一权威 LIST**，包含全部具体代码 + 全部模块。
> **路线图修正**（原 v2.0 写 v3.0 = 接估值层；现 v3.0 = 综合档）：**估值层版本号改为 v3.1**，v3.1 = 接估值层（等免费源拍板）。
> 下一次输出 = 2026-07-18 21:00 CST 周六。

---

## 0. 设计原则（v3.0 LOCKED）

- 一份文件 = 全部监控宇宙，不留"继承"指针
- 35 ETF + 100 股 + 8 Regime + 5 AI Overlay = **总监控池 148 个代码**
- 免费数据源 only（yfinance + RSS + EDGAR），无 paid API
- Cron 节奏 = 每周六 21:00 CST（不跑日报/盘中/demo）
- Appendix [approximate]：仅可拿 = 个股 forward PE/PB；不可拿 = ETF 资金流/ETF fwd-PE 5y 百分位/EPS Revision（proxy 误导禁止）

---

## 1. Market Regime（市场状态）— 8 项

| 代码 | 含义 | 用途 |
|---|---|---|
| SPY | 大盘 | 趋势锚 |
| QQQ | 成长 | 风险偏好 |
| IWM | 小盘 | 风险偏好 |
| ^VIX | 恐慌 | Risk On/Off 触发 |
| DX-Y.NYB | 美元 | 资金回流 |
| ^TNX | 10Y 收益率 | 利率 |
| ^FVX | 5Y 收益率 | 政策预期 |
| GC=F | 黄金 | 避险 |

**输出判断（v2.0 LOCKED）**：
- Risk On: QQQ > SPY、VIX 下降、10Y 下降 → 有利 AI / Software / Growth；不利 Utilities / Defensive
- Risk Off: 反之
- Transition: 信号分裂 → 标记"观察"

---

## 2. Sector Rotation（11 主板块 ETF）— 完整名单

| ETF | 板块 | 代表股 |
|---|---|---|
| XLC | 通讯服务 | META, GOOGL, NFLX, DIS, T, VZ, CHTR, TMUS |
| XLY | 非必需消费 | AMZN, TSLA, HD, MCD, NKE, SBUX, LOW, BKNG, TJX, GM |
| XLP | 必需消费 | WMT, COST, PG, KO, PEP, PM, MO, CL, MDLZ |
| XLE | 能源 | XOM, CVX, COP, SLB, EOG, MPC, PSX, OXY, KMI |
| XLF | 金融 | BRK-B, JPM, BAC, WFC, GS, MS, C, AXP, SCHW, BLK |
| XLV | 医疗保健 | LLY, UNH, JNJ, ABBV, MRK, TMO, ABT, AMGN, GILD, ISRG |
| XLI | 工业 | GE, CAT, RTX, UBER, HON, UNP, BA, DE, LMT, UPS |
| XLB | 材料 | LIN, SHW, FCX, ECL, NEM, APD, NUE, DOW |
| XLRE | 房地产 | PLD, AMT, EQIX, WELL, SPG, O, PSA, DLR |
| XLK | 科技 | NVDA, MSFT, AAPL, AVGO, ORCL, CRM, AMD, ADBE, QCOM, CSCO |
| XLU | 公用事业 | NEE, SO, DUK, CEG, VST, AEP, SRE, D |

---

## 3. Sub Industry（24 子板块 ETF）— 完整名单

### 通讯 / 消费
- IYZ — 电信
- XRT — 零售
- ITB — 住宅建筑
- PEJ — 休闲与娱乐

### 能源 / 金融
- XOP — 油气勘探与生产
- OIH — 油田服务
- KRE — 区域银行
- KIE — 保险

### 医疗
- IBB — 大中型生物科技
- XBI — 等权生物科技
- IHI — 医疗器械

### 工业 / 运输 / 国防
- ITA — 航空航天与国防
- XAR — 等权航空航天与国防
- IYT — 运输
- PAVE — 美国基础设施

### 材料 / 房地产 / 公用事业
- GDX — 金矿股
- SIL — 银矿股
- VNQ — 美国 REIT
- IDU — 公用事业

### 科技
- SMH — 半导体（**v3.0 标记**：同时归入 AI Overlay）
- SOXX — 半导体等权
- IGV — 软件
- HACK — 网络安全
- SKYY — 云计算

---

## 4. AI Theme Overlay（5 ETF）— v2.0 引入

| ETF | 方向 | 来源 |
|---|---|---|
| SMH | 半导体 | v1.0 已在 Sub Industry，v3.0 双归类 |
| BOTZ | 机器人 / AI | v2.0 新增 |
| ROBO | 自动化 | v2.0 新增 |
| CLOU | 云计算 | v2.0 新增 |
| GRID | AI 电力基础设施 | v2.0 新增 |

**v3.0 备注**：AI Overlay 与 Sub Industry 可双归类（同一代码两处出现不算数量膨胀）。

---

## 5. Sector Score v3.0 LOCKED 权重

| 维度 | 权重 |
|---|---|
| Momentum 1M | 15% |
| Momentum 3M | 20% |
| Relative SPY | 25% |
| Trend | 25% |
| Volume | 10% |
| News | 5%（仅作解释，不污染主评分）|

- Range: 0-100
- 决定时只看 1M / 3M / Rel / Trend / Volume
- News 仅用作报告文字解释

---

## 6. Stock Monitor（100 股 · 总数 LOCKED · 双 Tag）

**总数硬上限 = 100**（v3.0 / v2.1 / 路线图后续版本都不突破）。

### 6.1 100 股完整名单（按 Sector 分组）

**XLC (8)**: META, GOOGL, NFLX, DIS, T, VZ, CHTR, TMUS
**XLY (10)**: AMZN, TSLA, HD, MCD, NKE, SBUX, LOW, BKNG, TJX, GM
**XLP (9)**: WMT, COST, PG, KO, PEP, PM, MO, CL, MDLZ
**XLE (9)**: XOM, CVX, COP, SLB, EOG, MPC, PSX, OXY, KMI
**XLF (10)**: BRK-B, JPM, BAC, WFC, GS, MS, C, AXP, SCHW, BLK
**XLV (10)**: LLY, UNH, JNJ, ABBV, MRK, TMO, ABT, AMGN, GILD, ISRG
**XLI (10)**: GE, CAT, RTX, UBER, HON, UNP, BA, DE, LMT, UPS
**XLB (8)**: LIN, SHW, FCX, ECL, NEM, APD, NUE, DOW
**XLRE (8)**: PLD, AMT, EQIX, WELL, SPG, O, PSA, DLR
**XLK (10)**: NVDA, MSFT, AAPL, AVGO, ORCL, CRM, AMD, ADBE, QCOM, CSCO
**XLU (8)**: NEE, SO, DUK, CEG, VST, AEP, SRE, D

**合计：8+10+9+9+10+10+10+8+8+10+8 = 100 ✓**

### 6.2 Theme 双 Tag 映射（v2.0 引入，v3.0 完整化）

| 主题 | 涵盖股 |
|---|---|
| AI GPU | NVDA, AMD, AVGO, MU, MRVL |
| AI Power | VST, CEG, ETN, GEV, GE |
| AI Data Center | EQIX, DLR, AMT, O |
| AI Network | ANET, CSCO, CRDO |
| AI Software | PLTR, CRM, ORCL, ADBE, SNOW |
| Semi Equip | AMAT, LRCX, KLAC, TER, ON |

**v3.0 说明**：Theme 标签为额外维度，不改 Sector 主归类；同一股票可双 Tag。

---

## 7. Form 4 Insider（v1.0 + v2.0 一致）

- SEC EDGAR Form 4 抓买入信号（CEO / CFO / 董事买入）
- 区分税务卖出 vs 大额减持

---

## 8. Appendix [approximate] 数据源边界（v2.0 LOCKED）

### 可拿
| 字段 | 来源 |
|---|---|
| 个股 Forward PE（部分）| yfinance Ticker.info |
| 个股 P/B | yfinance Ticker.info |

### 不可拿（严禁输出 = 视为 `data unavailable`）
| 字段 | 原因 |
|---|---|
| ETF Forward PE / 5 年百分位 | yfinance quoteSummary 在本 IP 被 401 |
| ETF 资金流（流入 +$X.XB）| etf.com 403 / etfdb 403 / WSJ 401 / yfinance quoteSummary 401 / nasdaq 200 太精简 |
| EPS Revision | FactSet / Refinitiv 付费；FMP free tier 限速不稳 |

**这是 v3.0 硬边界**。任何"用 proxy 凑出来"的 fake data 都视为污染主报告。

---

## 9. 周报固定输出（v3.0）

1. **Market Regime** — 8 项 + Risk On/Off/Transition 判定
2. **11 主板块** — 周表现 + Sector Score 排序（Top 3 / Tail 3）
3. **24 子板块** — Top 8 + Tail 6
4. **AI Theme Overlay** — 5 ETF 周表现 + Score
5. **100 代表股** — 领涨 Top 12 / 领跌 Tail 10 / Volume Spike Top 12
6. **Form 4 Insider** — 本周买入信号
7. **Yahoo RSS** — 板块与代表股新闻（仅作解释，不进评分）
8. **Appendix [approximate]** — 个股 forward PE / PB 摘要
9. **结论 + 下周观察**

---

## 10. 路线图（v3.0 修正版）

| 版本 | 内容 | 状态 |
|---|---|---|
| v1.0 | 35 ETF + 100 股 | LOCKED（保留归档）|
| v2.0 | 8 模块 + Sector Score + AI Overlay + Appendix | LOCKED（保留归档）|
| **v3.0**（当前）| **去重整合一份权威 LIST 文件** | **LOCKED** |
| v3.1 | 接估值层（依赖 Finviz/FMP/Koyfin 等免费源拍板） | Pending |
| v3.2 | 接 EPS Revision（v3.1 后才评估）| Pending |
| v4.0 | 接 TradingView / Koyfin 付费 API | Pending |

---

## 11. LOCKED 边界（v3.0）

- **数量**：35 ETF + 5 AI Overlay (SMH 双归类) + 100 股 = 总宇宙硬上限 148 唯一代码
- **Cron**：`f84a872bf4a9` 周六 21:00 CST，调用 `us_market_sector_weekly_v2.py`
- **数据源**：仅 yfinance + Yahoo RSS + EDGAR；不接付费 API
- **附录**：严禁污染主报告；不可拿字段 = `data unavailable`
- **新闻 5%**：仅作解释，不入评分关键路径
- **v3.0 不增加任何新监控项**

---

## 12. 历史归档指向

- v1.0 列表定义：`US-MARKET-SECTOR-UNIVERSE-v1.0-LOCKED.md`（git `45ed8b9`）
- v2.0 架构定义：`US-MARKET-SECTOR-UNIVERSE-v2.0-LOCKED.md`（git `c54b4a3`）
- v3.0 合并：`US-MARKET-SECTOR-UNIVERSE-v3.0-LOCKED.md`（本文件，权威）
- Skill LOCKED：`market/us-market-sector-weekly`
- Cron：`f84a872bf4a9`
- 脚本：`/var/codex_project/hermes-home/profiles/bot-b/scripts/us-market-sector-weekly/us_market_sector_weekly_v2.py`
