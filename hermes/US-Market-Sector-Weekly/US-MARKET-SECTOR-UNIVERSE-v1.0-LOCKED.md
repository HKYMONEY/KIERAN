---
title: 美股板块周报 — 主板块 / 子板块 / 代表股
version: v1.0
status: LOCKED
updated: 2026-07-14
tags: [美股, 板块, ETF, 周报, locked]
---

# 美股板块周报监控池

> 只覆盖美国股票市场。主板块 11 个、子板块 24 个，共 35 只 ETF；代表股 100 只。该文件定义固定监控宇宙，不代表买卖建议。

## 1. 主板块（11 ETF）

- **通讯服务** — `XLC` — META, GOOGL, NFLX, DIS, T, VZ, CHTR, TMUS
- **非必需消费** — `XLY` — AMZN, TSLA, HD, MCD, NKE, SBUX, LOW, BKNG, TJX, GM
- **必需消费** — `XLP` — WMT, COST, PG, KO, PEP, PM, MO, CL, MDLZ
- **能源** — `XLE` — XOM, CVX, COP, SLB, EOG, MPC, PSX, OXY, KMI
- **金融** — `XLF` — BRK-B, JPM, BAC, WFC, GS, MS, C, AXP, SCHW, BLK
- **医疗保健** — `XLV` — LLY, UNH, JNJ, ABBV, MRK, TMO, ABT, AMGN, GILD, ISRG
- **工业** — `XLI` — GE, CAT, RTX, UBER, HON, UNP, BA, DE, LMT, UPS
- **材料** — `XLB` — LIN, SHW, FCX, ECL, NEM, APD, NUE, DOW
- **房地产** — `XLRE` — PLD, AMT, EQIX, WELL, SPG, O, PSA, DLR
- **科技** — `XLK` — NVDA, MSFT, AAPL, AVGO, ORCL, CRM, AMD, ADBE, QCOM, CSCO
- **公用事业** — `XLU` — NEE, SO, DUK, CEG, VST, AEP, SRE, D

## 2. 子板块（24 ETF）

### 通讯 / 消费
- `IYZ` — 电信
- `XRT` — 零售
- `ITB` — 住宅建筑
- `PEJ` — 休闲与娱乐

### 能源 / 金融
- `XOP` — 油气勘探与生产
- `OIH` — 油田服务
- `KRE` — 区域银行
- `KIE` — 保险

### 医疗
- `IBB` — 大中型生物科技
- `XBI` — 等权生物科技
- `IHI` — 医疗器械

### 工业 / 运输 / 国防
- `ITA` — 航空航天与国防
- `XAR` — 等权航空航天与国防
- `IYT` — 运输
- `PAVE` — 美国基础设施

### 材料 / 房地产 / 公用事业
- `GDX` — 金矿股
- `SIL` — 银矿股
- `VNQ` — 美国 REIT
- `IDU` — 公用事业

### 科技
- `SMH` — 半导体
- `SOXX` — 半导体
- `IGV` — 软件
- `HACK` — 网络安全
- `SKYY` — 云计算

## 3. 周报固定输出

- 本周 SPY / QQQ / IWM 市场背景
- 11 个主板块：周涨跌、相对 SPY 强弱、20/50 日趋势
- 24 个子板块：强弱榜与轮动方向
- 100 只代表股：板块内领涨 / 领跌 / 异常成交量
- Yahoo Finance RSS：板块与代表股新闻
- SEC EDGAR：本周 8-K / 10-Q / 10-K / Form 4 重点披露
- 风险与下周观察项

## 4. LOCKED 边界

- **包含**：YAML、Skill、Cron、Memory、Obsidian。
- **仅免费数据源**：yfinance + RSS + EDGAR。
- **频率**：每周六，仅周报；不运行日报和盘中提醒。
- **范围**：仅美股；不加入 Crypto、大宗商品、非美股。
- **首次运行**：不跑 demo，等待首个周六正式运行。
