---
title: 野村投信（Nomura Asset Management Taiwan）
type: issuer
tags: [issuer, active-etf, nomura, foreign-invested-sitc, japanese]
slug: nomura
aliases: [野村投信, 野村證券投資信託, Nomura Asset Management Taiwan, NEXT FUNDS Taiwan, nomurafunds]
created: 2026-04-18
updated: 2026-04-18
sources:
  - raw/2026/04/18-nomura-00980a-official.md
---

# 野村投信（Nomura Asset Management Taiwan）

## TL;DR

**野村證券投資信託股份有限公司**，日系**外資投信**（Nomura Holdings 子公司）。發行**首批主動型 ETF 第一個掛牌**的 [[wiki/etfs/00980a|00980A 主動野村臺灣優選]]（2025-05-05）。主動型 ETF 線有 3 檔：00980A、**00985A 主動野村台灣 50**（首批）、**00999A 主動野村臺灣高息**（新增）。費率採 **flat 0.75%**——與另一家外資 [[wiki/issuers/allianz|安聯]] flat 0.7% 同組，構成 **「外資投信 flat signature」** vs 本土階梯 的第二個資料點。英文 ETF 使用「NEXT FUNDS」品牌（原為日本 Nomura 被動型 ETF 品牌），**台灣應用於主動型**，產生跨市場品牌混淆風險。

## Compiled Truth

### 基本資料

| 欄位 | 內容 |
|---|---|
| 全稱 | 野村證券投資信託股份有限公司 |
| 英文 | Nomura Asset Management Taiwan Ltd. |
| 母集團 | Nomura Holdings（日本野村證券）|
| 總部 | 台北市信義區信義路五段 7 號 30 樓 |
| 電話 | 02-8101-5501 |
| 官網 | https://www.nomurafunds.com.tw |
| ETF 專區 | https://www.nomurafunds.com.tw/ETFWEB/ |
| 日本 NEXT FUNDS 系列 | Nomura Asset Management 日本被動型 ETF 品牌，搬至台灣用於主動型 |

### 主動型 ETF 產品線（2026-04-18）

| 代號 | 名稱 | 性質 |
|---|---|---|
| [[wiki/etfs/00980a\|00980A]] | 主動野村臺灣優選 | **首批 6 檔第一個掛牌（2025-05-05）**、TAIEX TR 為基準 |
| 00985A | 主動野村台灣 50 | 首批 6 檔之一，TAIEX 50 相關（待 ingest）|
| 00999A | 主動野村臺灣高息 | 首批之後新增（待 ingest）|

→ 野村在主動型 ETF 類別**連發 3 檔**，是四家首批發行商裡產品最多的。

### 其他 ETF 清單

- **被動台股**：00935 野村臺灣新科技50、00944 野村趨勢動能高息
- **海外主題**：00960 野村全球航運龍頭、00972 野村日本動能高息、00971 野村美國研發龍頭、009812 野村日本東證ETF
- **債券**：00987B 野村10+澳洲公債

總計 **10 檔 ETF**（2026-04-18 野村官網配息頁確認）。

### 揭露風格特徵

見 [[wiki/mechanisms/issuer-voluntary-disclosure]] 四家跨投信比較。野村的特徵：

#### - 配息組成完全不揭露

野村 ETF 配息頁（nomurafunds.com.tw/ETFWEB/dividend_list）表格**只有 6 欄**：配息月份、每單位配息、當期配息率、評價日、除息日、發放日。**無可分配淨利益 vs 本金% 拆解**。跟群益、安聯一致——只合規 SITCA 函「內部留存紀錄」底線。

#### - 無常駐溢價警告

野村官網 disclaimer 為**一般性風險聲明**，未針對 00980A 發溢價警告（00980A 本身月均折價 -0.22%，也沒這個需求）。

#### + 申購/買回條款完整揭露

產品頁 `product-description?fundNo=00980A` 完整列出：每基數 500,000 受益權單位、預收 110%、申購費 0.10%、買回費 0.40%、處理費 2,000/基數、T+3 付款。透明度高。

#### + 收益分配條款明文公告

產品頁直接寫出「基金成立日起屆滿 120 天後，以每年一月、四月、七月及十月最後一個日曆日為收益評價日」——首次評價日受約束，對散戶理解配息排程有幫助。

### 費率結構

**00980A 經理費 flat 0.75%**（Yahoo、MoneyDJ、官網三處一致）：
- 保管費 0.035%（與群益相同，低於統一的 0.10–0.12%）
- 總管理費用 1.07%（含 0.32% 非管理費用，MoneyDJ 已滿一年有數據）

→ flat 模型與本土投信（統一/群益）200 億階梯斷點結構**顯著不同**。

## 我觀察到的漏洞 / 不對稱

### 1. NEXT FUNDS 品牌跨市場意義不一致 `[speculation]`

英文全名「**NEXT FUNDS** – Nomura Taiwan SMART Select Active ETF」。「NEXT FUNDS」本為 Nomura Asset Management 日本的**被動型 ETF 品牌**（>50 檔，全部指數追蹤）。台灣 00980A 是**主動型**。

**跨市場混淆風險**：
- 日本散戶看到「NEXT FUNDS」→ 認知為被動型
- 台灣散戶看到「主動野村臺灣優選」+ 英文「NEXT FUNDS」→ 可能誤以為指數追蹤
- 國際投資人查詢「NEXT FUNDS」→ Nomura 既有被動認知 vs 台灣主動實況衝突

野村未在產品頁特別說明此差異。對應 [[wiki/mechanisms/issuer-voluntary-disclosure]] 延伸——**品牌重用的揭露責任缺位**。

需要 ingest：日本 NEXT FUNDS 品牌頁做跨市場對比。

### 2. 外資 flat 費率可能有共同制度背景 `[speculation]`

安聯 flat 0.7% + 野村 flat 0.75%。兩家外資都不採用本土投信的 200 億階梯。**可能原因**：
- 外資集團全球費率統一，不願為單一市場客製階梯
- 日系/德系投信在本國主流為 flat ETF，搬到台灣沿用
- 外資規模較小（135 億、63 億）本身距 200 億斷點尚遠，設階梯對散戶無差別
- **本土投信「200 億以下 1.2% / 以上 1.0%」可能是 SITCA / 金管會的默認推薦而非強制**——外資選擇繞過

→ **SITCA 函是否對費率結構有任何「推薦格式」？** 待查 SITCA 官網法規文。

### 3. 首批掛牌 11 天後才有第二檔 `[fact]`

- 2025-05-05：00980A 野村（首檔）
- 2025-05-16：00982A 群益、00981A 統一（同日）
- 2025-05-19：其他首批

**野村「全台首檔」的行銷紅利只有 11 天**，此後 5 檔同期發行分食散戶資金。可能解釋為何 00980A 現在折價——行銷定位的先發優勢已被稀釋。

野村選擇搶首發的意圖：建立長期「台灣主動型 ETF 開創者」定位，換取散戶在未來類似產品湧現時的**品牌記憶點**。短期成交量或規模可能不是主要目標。

### 4. 殖利率 6.92% 是四檔最高但官網不強調 `[confirmed]`

00980A 殖利率為 4 家裡最高，但野村官網**不在產品頁顯著位置放殖利率**，定位用「長期成長性與穩定配息能力」。符合 SITCA 2026-02-09 函「不得主打高配息」精神。

但 Yahoo、MoneyDJ 會計算並刊載殖利率——**散戶實際接收的仍是高殖利率訊號**。SITCA 函規範不到第三方平台。

## Timeline

- **2026-04-18** — 首次建立 issuer 頁。第四家首批主動型 ETF 發行商。
- **2025-05-05** — 00980A 上市（全台首檔主動式 ETF）
- **2025-04-22** — 00980A 成立

## Related

- [[wiki/etfs/00980a]] — 旗艦主動型 ETF、全台首檔
- [[wiki/people/yu-ching-te]] — 00980A 經理人游景德（待建）
- [[wiki/issuers/uni-president]] — 本土投信對比 1
- [[wiki/issuers/capital-sitc]] — 本土投信對比 2
- [[wiki/issuers/allianz]] — 另一家外資投信（德系 flat 0.7%）
- [[wiki/mechanisms/active-etf-fee-disclosure]] — 外資 flat signature
- [[wiki/mechanisms/issuer-voluntary-disclosure]] — 四家揭露對比

## Sources

- [[raw/2026/04/18-nomura-00980a-official]]

## TODO

- ingest 00985A、00999A（野村另兩檔主動型 ETF）
- 取得野村所有 ETF 的配息組成政策是否一致
- 查日本 NEXT FUNDS 系列，比較主/被動品牌差異
- 野村 2025 年報（若有）檢視 00980A 實際週轉率
- 董事會/總經理資訊
- 建立 [[wiki/people/yu-ching-te]] 游景德經理人頁
