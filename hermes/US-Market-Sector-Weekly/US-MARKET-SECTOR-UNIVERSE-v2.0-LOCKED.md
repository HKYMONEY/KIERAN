---
title: US Market Radar 监控池 v2.0
version: v2.0
extends: US-MARKET-SECTOR-UNIVERSE-v1.0-LOCKED.md
status: LOCKED
updated: 2026-07-14
tags: [美股, Market Radar, v2, locked]
---

# US Market Radar 监控池 v2.0

> 在 v1.0 基础上扩展 8 模块架构。35 ETF + 100 股总数保持不变。免费数据源 only。
> 路线图：v2.0（主报告） → v2.1（AI Overlay 标签细化） → v3.0（估值/EPS） → v4.0（接 TradingView API）

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

**输出判断**：
- Risk On: QQQ > SPY、VIX 下降、10Y 下降 → 有利 AI / Software / Growth；不利 Utilities / Defensive
- Risk Off: 反之
- Transition: 信号分裂 → 标记"观察"

## 2. Sector Rotation（11 主板块 ETF）— v1.0 继承
同 v1.0 LOCKED。

## 3. Sub Industry（24 子板块 ETF）— v1.0 继承
同 v1.0 LOCKED。

## 4. AI Theme Overlay（5 ETF，**新增**）
| ETF | 方向 |
|---|---|
| SMH | 半导体（v1.0 已含，重定位为 AI 主题） |
| BOTZ | 机器人/AI |
| ROBO | 自动化 |
| CLOU | 云计算 |
| GRID | AI 电力基础设施 |

## 5. Sector Score（**新增维度**）
**权重 v2.0 LOCKED**：
- Momentum 1M  15%
- Momentum 3M  20%
- Relative SPY 25%
- Trend        25%
- Volume       10%
- News          5%（仅作解释，不污染主评分）
- Range 0-100

**新闻权重 5% 仍保留，但实际决定时只看 1M/3M/Rel/Trend/Volume；新闻主要用于报告中的文字解释。**

## 6. Stock Monitor（100 股，**总数不变**）
v1.0 LOCKED 100 股 + v2.0 新增 **多维 Theme 标签**：
- 同股多 Tag：例如 VST = Sector(Utility) + Theme(AI Power)
- EQIX = Sector(Real Estate) + Theme(AI Data Center)
- ANET = Sector(Technology) + Theme(AI Network)

**v2.0 不增加新股票到 100 股里**；v2.1 才在总数内调整主题映射。

## 7. Form 4 Insider — v1.0 继承
SEC EDGAR Form 4 抓买入信号（CEO/CFO/董事买入）。

## 8. Appendix [approximate]（**后台实验层**）
**规则**：严禁进入主评分，只列免费源能拿到的近似值。

| 可拿 | 来源 |
|---|---|
| 个股 Forward PE（如 NVDA 15.9） | yfinance Ticker.info |
| 个股 P/B | yfinance Ticker.info |

| 不可拿（**禁止输出**） | 原因 |
|---|---|
| ETF Forward PE / 5 年百分位 | yfinance quoteSummary 在这台 IP 被 401 |
| ETF 资金流（流入 +$1.2B） | etf.com 403 etfdb 403 WSJ 401 nasdaq 200 太精简 |
| EPS Revision | FactSet/Refinitiv 付费；FMP free tier 限速不稳 |

**这是 v2.0 的硬边界**。如果违反，等于 proxy 误导主报告。

## 9. 周报固定输出（v2.0）

1. **Market Regime**：8 项 → 状态判定 + 有利/不利
2. **11 主板块** + 24 子板块：周表现 + Sector Score v2.0
3. **AI Theme Overlay**：5 ETF 周表现与轮动方向
4. **100 代表股**：领涨/领跌/Volume Spike
5. **Form 4 Insider**：本周买入信号
6. **Appendix [approximate]**：个股 Forward PE 摘要（如 NVDA 15.9、P/B）
7. **结论与下周观察**

## 10. LOCKED 边界（v2.0）

- **数量**：35 ETF + 100 股不变。
- **模块**：8 个已写明。
- **数据**：仅 yfinance + RSS + EDGAR；不接付费 API。
- **Appendix 边界**：仅可拿 → 仅输出个股 forward PE；不可拿 → 标注 "data unavailable"。
- **新闻**：仅作解释，不进评分关键路径。
- **路线图**：v2.1（股内 Theme） / v3.0（估值层） / v4.0（TradingView API）。
