# Operations Log

每次 wiki ingest / 結構改動的記錄。新的在上面。

---

## 2026-04-18 — 第二輪 ingest：申贖機制 + 全市場成交驗證

**時間**：2026-04-18（cron loop round 2）
**觸發**：CronCreate 排程（每半小時一次，不發 Threads）

**Raw 新增**：
- `raw/2026/04/18-twse-etf-ranking.md` — TWSE e添富 機構園地擷取全市場統計與 Top 10 成交排行

**Wiki 新增**：
- `wiki/mechanisms/creation-redemption.md` — ETF 申贖機制頁（實物 vs 現金申贖、AP 套利、主動型的透明度—套利兩難）

**Wiki 更新**：
- `wiki/etfs/00981a.md` — Timeline 加入「單日成交 #1 (128 億)」項目，Sources 加入 TWSE ranking

**Index 更新**：加入 creation-redemption 列，Open Questions 新增 #6（成交量 #1 的意義）

**關鍵發現**：
1. **00981A 單日成交 128.18 億全市場 #1**，超越 0050（85 億）。主動型 ETF 已擠進成交榜前段（#1 和 #5 都是主動型）
2. **日成交 / AUM ≈ 8.8%**，高速換手，作為 0.67% 非管理費用的量化背景
3. **全市場 ETF 規模 59,369 億 / 221 檔 / 1,640 萬受益人次**，00981A 單檔佔 2.44%
4. **透明度—套利兩難**命題確立：主動型為保 alpha 延遲揭露持股 → AP 套利效率下降 → 系統性溢折價

**失敗嘗試**：
- `twse.com.tw/zh/products/listed/ETF/overview.html` redirect 到首頁（URL 變動）
- 正確路徑：`/zh/ETFortune-institute/index`

**TODO for 下一輪**：
- 讀 00981A 公開說明書「申購與買回」章節（AP 名單、申購費率、creation unit 大小）
- 查 00981A 是否曾暫停申購或有申購上限
- ingest 另一檔主動型 ETF（00992A，成交 #5）做對比
- 查主動型 ETF 持股揭露頻率的法規要求（SITCA 或 FSC）
- 找 00981A 收益平準金配息拆解（[[wiki/mechanisms/income-equalization]] 待建）

---

## 2026-04-18 — 首次 ingest：00981A

**時間**：2026-04-18 (manual)
**觸發**：minghua 手動要求，作為 repo 首次 ingest 種子

**Raw 新增**：
- `raw/2026/04/18-00981a-yahoo-profile.md` — Yahoo 股市 profile 頁擷取
- `raw/2026/04/18-00981a-moneydj-basic.md` — MoneyDJ 基本資料頁擷取

**Wiki 新增**：
- `wiki/etfs/00981a.md` — 00981A 主動統一台股增長（主頁）
- `wiki/issuers/uni-president.md` — 統一投信（stub + TODO）
- `wiki/mechanisms/active-etf-fee-disclosure.md` — 主動型 ETF 費用揭露機制

**Index 更新**：加入三個 page 的列表

**關鍵發現**：
1. **費用揭露不對稱**：Yahoo 1.0% vs MoneyDJ 1.67%（總管理費用），差額 0.67% 是非管理費用
2. **「創新能力」敘事 vs 前 300 大 60% 限制**的產品/行銷矛盾
3. **持續溢價**：月均 0.29%、4/17 達 0.64%
4. **規模爆量**：998 億（3/31）→ 1,450 億（4/17）= 單月 +45%

**失敗嘗試**：
- MOPS 首頁 redirect，未找到 00981A 直達 URL
- Google / DDG 搜尋被 captcha 擋
- Goodinfo 404
- 統一投信官網（uni-sitc.com.tw / uniasset.com.tw）DNS 都查不到，待找對的 domain

**TODO for 下一輪**：
- 找到統一投信官方 domain（可能是 `pfm.uniasset.com.tw` 或從 ezmoney.com.tw 反查）
- ingest 公開說明書 PDF（從 MoneyDJ「文件下載」連結）
- 抓 00981A 最新月報（持股明細、實際週轉率）
- ingest 其他主動型 ETF（00982A、00987A、00991A、00992A、00994A）以驗證費用揭露是否為系統性現象
- 查金管會 / 投信投顧公會對 TER 揭露的規範

---

## 2026-04-18 — Initial scaffold

- repo created：marvin-69-jpg/tw-stock-wiki（public）
- 架構照搬 agent-memory-research：raw/ wiki/ reports/ schema/ tools/ .claude/skills/
- Entity categories：etfs / issuers / mechanisms / regulations / events / people
- 首個研究種子：00981A（即將 ingest）
