---
title: 主動式 ETF 持股揭露（全透明每日揭露制）
type: mechanism
tags: [holdings-disclosure, full-transparency, active-etf, arbitrage, regulation]
slug: active-etf-holdings-disclosure
aliases: [持股揭露, 全透明揭露, full transparency, daily holdings disclosure, 投資組合揭露]
created: 2026-04-18
updated: 2026-04-18
sources:
  - raw/2026/04/18-twse-active-etf-overview.md
---

# 主動式 ETF 持股揭露（全透明每日揭露制）

## TL;DR

台灣主動式 ETF 採用**「全透明揭露」**設計：投信公司必須於**每營業日基金淨值結算後**，在官方網站揭露**當日實際投資組合**。這是比美國部分主動式 ETF（如 ARK、半透明 ActiveShares 結構）**更激進**的制度選擇——美國有半透明產品允許經理人每季才揭露完整持股以保護 alpha，台灣直接要求 **daily full disclosure**。

制度好處：AP 套利數據完整、投資人可監督、外界可檢視策略一致性。
制度代價：**經理人的 alpha 邊緣（edge）在 T+1 就可能被競爭者/量化 player 反向交易**，主動操作的保密價值大幅削弱。

## Compiled Truth

### 制度原文（TWSE 官方敘述）

來源：[[raw/2026/04/18-twse-active-etf-overview]]（TWSE e添富「臺灣主動式 ETF 發行現況」）

> 主動式 ETF 投資組合採用「全透明揭露」設計，投信公司於**每營業日基金淨值結算後**，須在其官方網站**揭露當日實際投資組合**，讓投資人能更清楚掌握基金操作方向。然投資人需注意，由於主動式 ETF 的操作彈性，基金經理人**可在次一營業日進行投資組合調整**，因此**盤中投資組合不一定與前一日公布之投資組合內容相同**，盤中揭露的即時預估淨值資訊，亦可能受到盤中投資組合調整及匯率波動等因素影響，而與實際淨值產生誤差。

### 揭露時間線（T 日 vs T+1）

```
T 日盤後 → 淨值結算 → 投信官網揭露 T 日收盤組合
T+1 日開盤 → 經理人可基於 T 日組合 + 策略 + 市況進行調整
T+1 日盤中 → 投資人看到的「上一日持股」可能已經被調動
T+1 日盤後 → 揭露 T+1 日收盤組合（更新）
```

**最大時間落差**：從揭露瞬間到次日盤中調整，可以有 **24 小時以內**的窗口內投資組合「實際與揭露不同」。

### 跨市場比較

| 市場 | 主動式 ETF 揭露頻率 | 代表產品 |
|---|---|---|
| 台灣 | **每日（T+1 盤前揭露 T 日組合）**| 首批 6 檔（00980A–00985A） |
| 美國 Fully Transparent | 每日 | ARKK, JEPI, JEPQ |
| 美國 Semi-Transparent (ActiveShares, Precidian 等) | **每季**（類似共同基金）| 部分主動型 ETF |
| 美國 Proxy Portfolio | 每日代理組合 + 每季實際組合 | 部分產品 |

→ 台灣**統一採行 fully transparent**，沒有提供 semi-transparent 結構給業者選擇。這是**制度層的一次性選擇**，決定了台灣主動式 ETF 的運作樣貌。

### 揭露位置

各發行商官網。例如：
- 統一投信（[[wiki/etfs/00981a|00981A]]）：https://www.ezmoney.com.tw/ETF/Fund/Info?fundCode=49YTW
- 群益投信（[[wiki/etfs/00992a|00992A]]）：https://www.capitalfund.com.tw/etf/product/detail/500

**待查**：證交所是否有統一揭露入口（方便跨產品比較），還是只能各投信各看？

## 我觀察到的漏洞 / 不對稱

### 1. T+1 揭露 vs 盤中實際組合的套利視窗 `[confirmed by TWSE 原文]`

TWSE 明白指出「盤中投資組合不一定與前一日公布之投資組合內容相同」。這意味著：

- **AP 看到的 T+1 開盤組合 ≠ 基金真實組合**（除非經理人當天不動）
- iNAV（盤中預估淨值）基於 T 日組合 + 當日成分股價計算，**與實際 NAV 有誤差**
- AP 套利時面對的基礎是「稍微過時」的數據

**對套利效率的影響**：套利門檻被**經理人當日調整的不確定性**推高。如果經理人常常盤中大幅調整，AP 要加上**組合漂移風險溢酬**才敢建籃，套利進場門檻更高 → 溢折價需要累積到更大才收斂。

→ 這**補強**了 [[wiki/etfs/00981a|00981A]] 月均溢價 0.29%（見 [[wiki/mechanisms/creation-redemption]]）的結構性解釋：不是每季才揭露造成的，而是**每日揭露但有 T+1 漂移**的次佳設計後果。

### 2. Alpha 邊緣的快速衰減 `[speculation]`

「經理人操作」與「持股全透明」本質上有張力：
- 經理人看到某個冷門小型股低估 → 建倉
- T+1 盤後 → 全市場看到基金新進這支股 → **資訊從「經理人獨享」變「全市場共享」**
- 其他量化交易者、跟投策略、甚至競爭主動 ETF 立刻反應
- 經理人的 alpha 邊緣被**稀釋**

→ 要維持 alpha，經理人需要**大量、快速、精準**的新點子，或轉向**規模大、流動性好**的個股（這讓組合朝 0050-like 趨近）。這可能是為什麼 00981A 有「前 300 大 60%」限制——**策略實務上就往大型股靠**，全透明進一步強化這個趨勢。

### 3. 揭露入口分散不利跨產品比較 `[speculation]`

目前必須各自到發行商官網查持股。這讓散戶/研究者**無法方便做跨產品比較**（例如 00981A vs 00992A 的 Top 10 重疊度、集中度變化）。

待查：TWSE 或 SITCA 是否有**統一 portal** 匯總所有主動式 ETF 的當日持股。若無，這是**資訊基礎設施層的漏洞**。

### 4. 「全透明」與收益平準金的配息組成不透明形成對比 `[confirmed]`

同一檔主動式 ETF：
- **持股組合：每日揭露**（full transparency）
- **配息組成拆解：未要求對外揭露**（見 [[wiki/mechanisms/income-equalization]]）

**有趣的監管不對稱**：
- 投資標的 → 極度透明（保護投資人知情）
- 配息來源 → 黑盒子（投信內部留存紀錄即可）

揭露取捨看起來**偏重「你買了什麼」而忽略「你拿到的錢從哪裡來」**。對散戶的實質保護落差很大——持股透明但大多數人看不懂/不會看；配息金額誰都看得懂但拆解不揭露。

## Timeline

- **2024 年底** — 金管會開放主動式 ETF 發行，確立「全透明揭露」制度
- **2025-05-05** — 首檔主動式 ETF（00980A）掛牌，制度開始實際運行
- **2026-04-18** — 本頁建立，主要依據 TWSE 2025 年底官方文章（[[raw/2026/04/18-twse-active-etf-overview]]）

## Related

- [[wiki/etfs/00981a]] — 首批之一，持股揭露於 ezmoney.com.tw
- [[wiki/etfs/00992a]] — 群益首批，持股揭露於 capitalfund.com.tw
- [[wiki/mechanisms/creation-redemption]] — T+1 揭露與 AP 套利效率的連結
- [[wiki/mechanisms/active-etf-fee-disclosure]] — 對稱的揭露不足（費用）
- [[wiki/mechanisms/income-equalization]] — 對比的揭露不足（配息組成）
- [[wiki/events/2025-taiwan-active-etf-launch]] — 制度開放事件（待建）

## Sources

- [[raw/2026/04/18-twse-active-etf-overview]] — TWSE 官方「臺灣主動式 ETF 發行現況：從創新到躍進」

## TODO

- 取得金管會 2024 年底開放主動式 ETF 的具體函文
- 取得證交所「資訊揭露標準」對主動式 ETF 的細則原文
- 查 TWSE 或 SITCA 是否有統一持股查詢 portal
- 實際檢視 00981A 在 ezmoney.com.tw 上當日持股如何呈現（格式、完整度、下載便利性）
- 對比 00981A 和 00992A 的 Top 10 持股重疊度（一次 snapshot 即可）
- 查「半透明」主動式 ETF 在美國市場的實務效果是否好於台灣「全透明」
