# Operations Log

每次 wiki ingest / 結構改動的記錄。新的在上面。

---

## 2026-04-18 — 第三輪 ingest：收益平準金 + SITCA 主動式 ETF 公告

**時間**：2026-04-18（cron loop round 3）
**觸發**：CronCreate 排程

**Raw 新增**：
- `raw/2026/04/18-sitca-active-etf-equalization.md` — SITCA 中信顧字第 1150050602 號函（2026-02-09，理事長尤昭文）完整逐字摘錄 + 解讀筆記

**Wiki 新增**：
- `wiki/mechanisms/income-equalization.md` — 收益平準金機制頁（含會計溯源、台灣法規演進時間線、主動型 vs 被動型差異、四個漏洞觀察）

**Wiki 更新**：
- `wiki/etfs/00981a.md` — 配息段補入制度背景說明（主動式 ETF 不強制揭露配息組成）
- `index.md` — 加入 income-equalization 列，Open Question #4 標記「部分回答」

**關鍵發現（最重要的一輪）**：
1. **找到 SITCA 主動式 ETF 收益平準金公告原文**（2026-02-09 中信顧字 1150050602）：
   - 主動式 ETF **不強制**參照指數息率決定配息率（被動型須遵循 112-11-13 函的「當期指數息率」原則）
   - 即便設有 benchmark，也不需要綁
   - 內部合理說明並留存紀錄即可，**未要求對外揭露**
2. **行銷加嚴**：明文禁止「以高配息作為宣傳重點」，顯示業界已有此行為須糾正
3. **監管不對稱**：配息率鬆綁（裁量權大）+ 行銷緊縮（不許用這個裁量權做誘因）+ 對外揭露空缺
4. **散戶黑盒子**：00981A 2025-Q4 配 0.41 元，拆解不公開 → 新進受益人可能在補貼老受益人的配息

**技術紀錄**：
- SITCA 詳細頁是 ASP.NET postback，直接 agent-browser click 不生效，改用 `eval("detail2('docId','')")` 觸發
- 附件 PDF 透過 `member.sitca.org.tw` 有 session-bound URL，當次可直接 curl 下載

**TODO for 下一輪**：
- 取得金管會 112 年 11 月 13 日函（1120358072）— 被動型 ETF 收益平準金基準文件
- 取得金管會 115 年 2 月 3 日函（1140386328）— 主動型上位函（SITCA 是轉文）
- ingest 00981A 2025-Q4 配息公告，實際拆解收益組成
- ingest 另一檔主動型 ETF（00992A、00987A）對比配息政策
- 建立 `wiki/events/2024-high-dividend-etf-controversy` 事件頁（高股息 ETF 配息爭議餘波）

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
