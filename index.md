# TW Stock Wiki — Index

> Auto-maintained by LLM. Do not edit manually.

研究主題：**台灣主動型 ETF 的體制與機制漏洞**。

> **2026-04-18 Round 24 Meta-correction**：首次用 TWSE primary source（ETF e添富投資篩選器）抓完整主動式 ETF 母體，發現 Round 1-23 的 Yahoo-based gap discovery **漏了 5 檔 ETF + 4 家投信**（富邦、摩根、兆豐、聯博），遺漏率 26%。見 `raw/2026/04/18-twse-active-etf-master-list.md`。本次新增 TODO 優先 ingest 缺口。
>
> **2026-04-18 Round 37 Meta-correction²**：Round 24 TWSE audit 本身有盲區 —— **TWSE 篩選器只含 TWSE 上市、不含 TPEx 上櫃**。聯博 00980D（2025-07-24 成立、TPEx）為**D 字尾真正首檔**但 Round 24 未見。TPEx 其他案：00998A（Round 22）、00986D（Round 30）皆個案發現。**第 16 種揭露不對稱候選：TWSE primary audit 不含 TPEx**。
>
> **2026-04-18 Round 42（TPEx 補完第 2 檔、母體關閉）**：ingest **00985D 主動貝萊德優投等**（Yahoo primary、貝萊德投信首檔 ETF、**第 15 家投信正式建立**、BlackRock Taiwan / iShares 品牌）+ 首建 `wiki/issuers/blackrock-taiwan.md`。**外資首檔 ETF = D 字尾投等** 模式確立（聯博 + 貝萊德雙例）。**外資投等 D 字尾保管費結構 100% 相同**（2 段階梯 0.12/0.08%、斷點 300 億）、管理費貝萊德比聯博低 0.10-0.15 pp = **D 字尾管理費最低 0.45%**。**iShares 品牌明文嵌入基金名稱**（外資自家子品牌首見）。**Yahoo 推薦演算法完全斷裂**（推薦全為台股大盤股、無任何債券 ETF 同儕）= 第 17 種揭露不對稱候選。**TPEx 主動 ETF 母體至本輪全部 ingest**（5 檔全完成）。
>
> **2026-04-18 Round 41（TPEx 補完第 1 檔）**：ingest **00981D 主動中信非投等債**（Yahoo primary、中信第 3 檔 / 首檔 D 字尾 / 首檔債券 / D 字尾實際第 2 檔）。**中信分歧邏輯升維**：Round 22 純地域 → **地域 + 資產類型雙維**（全研究首個雙維分歧投信）。**保管費三段階梯第 2 例**（斷點 100/200 億 ≠ 富邦 100/300 億）= 三段非「富邦簽名」。**中信 = 第 2 家跨 TWSE+TPEx 佈局投信**（同聯博）。剩餘 TPEx 缺口：00985D 貝萊德（第 15 家投信）。
>
> **2026-04-18 Round 40 Meta-correction³（TPEx primary audit）**：抓 TPEx 主動式 ETF 商品頁（`https://www.tpex.org.tw/zh-tw/product/etf/product/active.html`）列 **5 檔**，本研究先前只 ingest 3 檔，**新發現 2 檔**：(1) **00981D 主動中信非投等債**（2025-09-16 上櫃、中信第 3 檔、中信首檔 D 字尾、D 字尾實際第 2 檔）、(2) **00985D 主動貝萊德優投等**（2026-03-30 上櫃、**貝萊德投信 = 第 15 家投信**、BlackRock Taiwan）。**D 字尾總檔數修正為 7 檔**（非 Round 37/38 記的 5 檔）、**TPEx 佔 4/7（57%）**。前 2 檔 D 字尾（00980D + 00981D）都掛 TPEx → **D 字尾早期上市地偏好 TPEx**。見 `raw/2026/04/18-tpex-active-etf-master-list.md`。

## Range Gaps（2026-04-18 primary source audit）

### TPEx 主動 ETF 完整母體（Round 40 新增）

| 代號 | 簡稱 | 上櫃日 | 本研究狀態 |
|---|---|---|---|
| 00998A | 主動復華金融股息 | 2026-04-15 | ✅ Round 22 ingest |
| 00986D | 主動復華金融債息 | 2026-04-15 | ✅ Round 30 ingest |
| **00985D** | **主動貝萊德優投等** | **2026-03-30** | ✅ **Round 42 ingest（第 15 家投信、BlackRock Taiwan、首檔 D 字尾投等）** |
| **00981D** | **主動中信非投等債** | **2025-09-16** | ✅ **Round 41 ingest（中信第 3 檔、首檔 D 字尾 + 首檔債券）** |
| 00980D | 主動聯博投等入息 | 2025-08-04 | ✅ Round 37 ingest |

### 原 TWSE audit 漏掉的主動 ETF（依代號）：
| 代號 | 名稱 | 上市日 | 規模 | 發行人 | 漏掉原因 |
|---|---|---|---|---|---|
| ~~00982D~~ | ~~主動富邦動態入息~~ | ~~2025.09.30~~ | ~~8.81 億~~ | ~~富邦~~ | ✅ Round 28 ingest（發現實際成立 2025-09-30，早於 TWSE 列表 10/14）|
| ~~00983D~~ | ~~主動富邦複合收益~~ | ~~2025.09.30~~ | ~~10.32 億~~ | ~~富邦~~ | ✅ Round 28 ingest |
| ~~00984D~~ | ~~主動聯博全球非投~~ | ~~2026.02.04~~ | ~~13 億~~ | ~~聯博~~ | ✅ Round 29 ingest（成立 2026-01-22）|
| ~~00989A~~ | ~~主動摩根美國科技~~ | ~~2025.10.22~~ | ~~18 億~~ | ~~摩根~~ | ✅ Round 26 ingest |
| ~~00993A~~ | ~~主動安聯台灣~~ | ~~2026.02.03~~ | ~~**126 億**~~ | ~~安聯~~ | ✅ Round 31 ingest（成立 2026-01-20，125.5 億）|

**漏掉的投信**：富邦（首批主動債券 ETF 發行者）、摩根（00989A 是入列證據）、兆豐（00996A）、聯博（00984D 外資）

## Structure

- `wiki/etfs/` — 個別 ETF
- `wiki/issuers/` — 投信發行商
- `wiki/mechanisms/` — 機制（申贖、配息、追蹤誤差⋯）
- `wiki/regulations/` — 法規
- `wiki/events/` — 事件
- `wiki/people/` — 經理人、決策者、研究者

## Wiki Pages

### ETFs

| Page | Summary | Tags | Last Updated |
|------|---------|------|-------------|
| [[wiki/etfs/00981a\|00981A — 主動統一台股增長]] | 統一投信旗艦主動型 ETF，1,450 億規模、費用揭露有落差 | active-etf, taiwan-equity, uni-president, large-cap-biased | 2026-04-18 |
| [[wiki/etfs/00992a\|00992A — 主動群益科技創新]] | 群益投信，科技主題，302 億規模、費用揭露第二種不對稱 | active-etf, taiwan-equity, capital-sitc, tech-innovation | 2026-04-18 |
| [[wiki/etfs/00984a\|00984A — 主動安聯台灣高息成長]] | 安聯投信（外資），63 億規模、flat 0.7% 費率、ETF 配息組成完全不揭露 | active-etf, taiwan-equity, allianz, high-dividend | 2026-04-18 |
| [[wiki/etfs/00980a\|00980A — 主動野村臺灣優選]] | 野村投信（外資日系），全台首檔主動式 ETF（2025-05-05）、135 億規模、flat 0.75% 費率、四檔中唯一月均折價 | active-etf, taiwan-equity, nomura, first-listing | 2026-04-18 |
| [[wiki/etfs/00983a\|00983A — 主動中信 ARK 創新]] | 中信投信（本土），首批唯一美股+年配+S&P500 基準、32.5 億規模、4 段階梯費率（推翻本土 2 段通例）| active-etf, us-equity, ctbc, ark-innovation, annual-dividend | 2026-04-18 |
| [[wiki/etfs/00982a\|00982A — 主動群益台灣強棒]] | 群益投信（本土），首批最大規模之一、363 億、**flat 0.8%**（推翻同發行商內費率一致通例）、連 9 漲未列警告 | active-etf, taiwan-equity, capital-sitc, first-batch, flat-fee | 2026-04-18 |
| [[wiki/etfs/00985a\|00985A — 主動野村台灣 50]] | 野村投信（外資日系）、首批最後 ingest、93 億、**flat 0.45%**（首批最低費率、增強指數型 benchmark Taiwan 50）、年配（首次 2026-12） | active-etf, taiwan-equity, nomura, first-batch, enhanced-indexing, flat-fee | 2026-04-18 |
| [[wiki/etfs/00987a\|00987A — 主動台新優勢成長]] | 台新投信（本土）、**非首批**（2025-12-30 上市）、22 億、**flat 0.75%**（**本土投信採 flat 首例**）、年配、**類別錯誤免責聲明**（被動模板貼主動頁）| active-etf, taiwan-equity, taishin, flat-fee, local-sitc | 2026-04-18 |
| [[wiki/etfs/00986a\|00986A — 主動台新龍頭成長（全球）]] | 台新投信（本土）、2025-08-27 上市、5.79 億、**經理費 1% + 保管費 0.25%**（跨國研究溢價 0.47%）、年配、全球股票、**類別錯誤 + 產品主題錯誤雙重揭露瑕疵** | active-etf, global-equity, taishin, cross-border, disclosure-error | 2026-04-18 |
| [[wiki/etfs/00999a\|00999A — 主動野村臺灣高息]] | 野村投信（外資日系）、**尚未掛牌**、flat **0.70%**、季配（2/5/8/11）、游景德兼任 00980A、**完成野村 3 檔光譜**（0.45/0.70/0.75），推翻 Round 12 假說，Round 15 新「裁量權」假說 | active-etf, taiwan-equity, nomura, high-dividend, flat-fee, pre-listing | 2026-04-18 |
| [[wiki/etfs/00997a\|00997A — 主動群益美國增長]] | 群益投信（本土）、2026-03-30 成立、**跨國美股首檔群益主動 ETF**、104.59 億（19 天日均 +5.5 億）、**階梯 1.2%/1.0% 同 00992A**、保管費 **0.1%–0.12%（3 倍台股）**、吳承恕、**推翻 Round 15 裁量權假說在群益的普適性** | active-etf, us-equity, capital-sitc, cross-border, tiered-fee | 2026-04-18 |
| [[wiki/etfs/00988a\|00988A — 主動統一全球創新]] | 統一投信（本土）、2025-10-21 成立、**統一首檔跨國全球主動 ETF**、212.15 億、**階梯 1.4%/1.2%（+0.2 pp 平移）**、保管費 0.10%–0.12%（**跨國無溢價**）、陳意婷、**推翻 Round 16 跨國保管費系統性溢價歸納** | active-etf, global-equity, uni-president, cross-border, tiered-fee | 2026-04-18 |
| [[wiki/etfs/00990a\|00990A — 主動元大 AI 新經濟]] | 元大投信（本土最大）、**2025-12-02 成立、元大首檔主動 ETF、直接跳過台股切入全球 AI**、254.17 億、**雙 flat：管理 0.9% + 保管 0.15%（本土 flat 第 3 家）**、**跨國主動 ETF 當前總負擔最低 1.05%**、吳昭豪、連 4 漲 6.03% | active-etf, global-equity, yuanta, cross-border, flat-fee, ai-theme | 2026-04-18 |
| [[wiki/etfs/00991a\|00991A — 主動復華未來 50]] | 復華投信（本土、華南金）、**2025-12-09 成立、復華首檔主動 ETF**、309.11 億、**階梯 1.0%/0.8%**、**半年配（本研究首見）**、benchmark TAIEX 總報酬、選股池前 150 大、呂宏宇、**警語嵌名（中信後本土第 2 家）**、揭露品質高端（4 維選股策略 + 20 個股舉例）、**Round 15 裁量權假說跨投信首次支持** | active-etf, taiwan-equity, fuhwa, tiered-fee, semi-annual-dividend, warning-in-name | 2026-04-18 |
| [[wiki/etfs/00994a\|00994A — 主動第一金台股優]] | 第一金投信（本土、推定第一金控）、**2025-12-26 成立、第一金首檔主動 ETF（第 9 家投信）**、24.28 億、**flat 0.70%（本土 flat 第 4 家且最低）**、保管費 flat 0.035%、benchmark 臺灣 50 指數、名稱「趨勢優選」**benchmark 與名稱策略對應模糊**、張正中、連 4 漲 8.84%、Yahoo 瀏覽第 4 名但規模低、**低費率+低規模陷阱** | active-etf, taiwan-equity, first-financial, flat-fee, taiwan-50-benchmark | 2026-04-18 |
| [[wiki/etfs/00995a\|00995A — 主動中信台灣卓越]] | 中信投信（本土、中信金控）、**2026-01-13 成立、中信第 2 檔主動 ETF**、44.87 億、**flat 0.75%** + 保管 flat 0.035%、Yahoo benchmark 欄位空白、張書廷、**中信同發行商內費率結構不一致：台股 flat vs 美股 4 段階梯**、**分歧邏輯 = 地域（同台新）**、**本土台股 flat 0.75% 雙例**（繼 00987A 台新）、**警語嵌名 Round 19 歸納部分削弱**（00995A 未嵌警語 vs 00983A 嵌入）| active-etf, taiwan-equity, ctbc, flat-fee, second-from-issuer | 2026-04-18 |
| [[wiki/etfs/00998a\|00998A — 主動復華金融股息]] | 復華投信（本土、推定華南金）、**2026-03-31 成立、復華第 2 檔主動 ETF、櫃 ETF TPEx 首見、傘型基金子基金首見**、28.42 億（3 週）、**階梯 1.2%/1.0%** + 保管 0.10%~0.14%、**全球金融股+股息策略**、張正宇、**復華分歧邏輯 = 地域（第 3 家地域分歧）**、**警語嵌名官網加長版**（含「且本基金並無保證收益及配息」）、**Round 21 Yahoo 截斷誤判反削弱**——Round 19 警語嵌名歸納恢復效力 | active-etf, global-equity, fuhwa, cross-border, tiered-fee, otc-etf, umbrella-fund, warning-in-name, financial-sector | 2026-04-18 |
| [[wiki/etfs/00400a\|00400A — 主動國泰動能高息]] | 國泰投信（本土、國泰金控）、**2026-03-30 成立 / 2026-04-09 上市**（Round 24 TWSE 驗證修正）、國泰首檔主動 ETF（第 10 家投信）、**8 交易日 127 億**（2026-04-17 TWSE 最新，原 Yahoo 19 天 107 億基準錯誤）、**flat 0.9%（本土 flat 0.9% 雙例，繼元大 00990A）** + **保管費罕見階梯 0.06%/0.04%（≤/>100 億）**、**動能（momentum）+ 高息 factor 首見 explicit 命名**、梁恩溢、官網 Access Denied（本土第 5 家抓取困難）| active-etf, taiwan-equity, cathay, flat-fee, momentum-strategy, high-dividend, custody-tiered | 2026-04-18 |
| [[wiki/etfs/00996a\|00996A — 主動兆豐台灣豐收]] | 兆豐投信（**第 11 家投信**、公股兆豐金控、SITCA A0001 老牌）、**2026-03-16 成立 / 2026-03-25 上市**、31 億、**flat 0.8% + flat 0.04%（本土 flat 0.8% 第 2 家，群益後）**、季配息、王仲良、**保管銀行元大商業銀行（跨集團交叉保管首見）**、Round 24 TWSE primary source audit 時首次發現 | active-etf, taiwan-equity, megabank-itim, flat-fee, quarterly-dividend, cross-group-custody | 2026-04-18 |
| [[wiki/etfs/00989a\|00989A — 主動摩根美國科技]] | 摩根投信（**第 12 家投信**、外資 J.P. Morgan）、**2025-10-14 成立 / 2025-10-22 上市（首批 6 檔後首檔跨國主動）**、17.80 億（6 個月慢增）、**flat 0.75% + flat 0.15%**（外資 flat signature）、美國科技、蓋欣聖單人、警語未嵌名、Yahoo 推薦從未觸及（Round 24 漏網最老案例、6 個月） | active-etf, us-equity, jpmorgan-taiwan, foreign-invested, flat-fee, tech-theme, cross-border | 2026-04-18 |
| [[wiki/etfs/00401a\|00401A — 主動摩根台灣鑫收]] | 摩根投信（外資 J.P. Morgan）、**2026-03-31 成立 / 2026-04-10 上市（摩根台股首檔）**、27.71 億（8 交易日）、**管理費 flat 0.60% = 全研究範圍最低**（破第一金 00994A 0.70%）、保管費 flat 0.045%、保管銀行國泰世華（跨集團）、**經理人首見核心+協管：沈馨 + 魏伯宇**、**Yahoo 經理人欄只顯示核心（協管遮蔽）= 第 14 種揭露不對稱**、Yahoo 名稱截斷「鑫收益→鑫收」（Round 22 截斷第 2 例）、連 6 漲 +7.98% 未警示 | active-etf, taiwan-equity, jpmorgan-taiwan, foreign-invested, flat-fee, high-dividend, core-coadjunct-manager, lowest-management-fee | 2026-04-18 |
| [[wiki/etfs/00982d\|00982D — 主動富邦動態入息]] | 富邦投信（**第 13 家投信**、本土富邦金控、Round 28 首建）、**2025-09-30 成立（主動債券 ETF D 字尾首見）**、8.81 億、**管理費階梯 0.45%/0.55%**、**保管費三段階梯 0.10/0.08/0.05%（首見三段）**、投資級債、全球、黃詩紋、**月配息首見**（2026-M3 配 0.052 元 / 4/20 除息）、**富邦優選收益傘型子基金**（傘型第 2 例，繼復華）| active-etf, active-bond-etf, d-suffix, fubon, cross-border, investment-grade-bond, umbrella-fund, monthly-dividend, tiered-custody-3step | 2026-04-18 |
| [[wiki/etfs/00983d\|00983D — 主動富邦複合收益]] | 富邦投信、**2025-09-30 成立（同傘姊妹）**、10.32 億、**管理費階梯 0.55%/0.65%（比 00982D +0.10 pp）**、**保管費三段階梯 0.10/0.08/0.06%**、複合收益債（疑含非投等）、全球、游陳達（同傘不同人）、**月配息** 0.06 元（年化 ≈ 7.05%）、**同傘內分歧邏輯 = 風險等級（第 5 種分歧邏輯）** | active-etf, active-bond-etf, d-suffix, fubon, cross-border, multi-sector-bond, umbrella-fund, monthly-dividend, tiered-custody-3step | 2026-04-18 |
| [[wiki/etfs/00984d\|00984D — 主動聯博全球非投]] | 聯博投信（**第 14 家投信**、外資美商 AllianceBernstein、Round 29 首建）、**2026-01-22 成立（主動債券 ETF 第 3 檔）**、12.86 億（3 個月）、**flat 0.80% + flat 0.12%**（外資 flat signature 延續至債券型）、**非投等債直白嵌名**、全球、陳俊憲、**月配息 0.085 元 = 年化 ≈ 10.07%（本研究最高殖利率）**、地址 **101 大樓 81 樓**、**Yahoo 推薦演算法對非投等債完全斷裂**（只推大盤股） | active-etf, active-bond-etf, d-suffix, alliancebernstein, foreign-invested, cross-border, high-yield-bond, non-investment-grade, flat-fee, monthly-dividend | 2026-04-18 |
| [[wiki/etfs/00985d\|00985D — 主動貝萊德優投等]] | 貝萊德投信（**第 15 家投信**、BlackRock Taiwan / iShares 品牌方、全球最大 AM 母集團 $10 兆 AUM、Round 42 首建）、**2026-03-20 成立 / 2026-03-30 上櫃 TPEx（成立→上櫃 10 天、D 字尾最短）**、9.09 億（D 字尾當前最低）、**管理費 2 段階梯 0.55/0.45%（D 字尾最低）+ 保管費 2 段階梯 0.12/0.08%（斷點 300 億，與聯博 00980D 100% 相同）**、全球投等債、游忠憲、**iShares 品牌明文嵌入基金名稱（外資自家子品牌首見）**、**外資首檔 ETF = D 字尾投等模式確立（聯博+貝萊德雙例）**、**Yahoo 推薦完全斷裂（全為台股大盤股、無任何債券 ETF 同儕）= 第 17 種揭露不對稱候選**、尚未首次配息 | active-etf, active-bond-etf, d-suffix, blackrock, ishares, global-bond, investment-grade, tiered-fee, tpex, foreign-invested, us-brand, first-from-issuer, lowest-d-suffix-management-fee | 2026-04-18 |
| [[wiki/etfs/00981d\|00981D — 主動中信非投等債]] | 中信投信（本土、中信金控、Round 41 ingest）、**2025-09-03 成立 / 2025-09-16 上櫃 TPEx**（D 字尾實際第 2 檔、晚聯博 00980D 約 1.5 個月早富邦 00982D 2 週）、**中信第 3 檔主動 ETF + 首檔 D 字尾 + 首檔債券 ETF**、72.47 億、**管理費 2 段階梯 0.75/0.65% + 保管費 3 段階梯 0.10/0.08/0.06%（100/200 億斷點 ≠ 富邦 100/300 億）**、陳昱彰、月配 0.07 元、美國非投等、**推翻 Round 22 中信純地域分歧 → 地域 + 資產類型雙維（全研究首個雙維分歧投信）**、**中信跨 TWSE+TPEx 佈局（第 2 家跨所投信、同聯博）**、Yahoo 推薦全被動非投等債（主動無同儕、同 Round 29 斷裂） | active-etf, active-bond-etf, d-suffix, ctbc, us-bond, non-investment-grade, tiered-fee, tiered-custody-3step, monthly-dividend, tpex, cross-exchange-issuer | 2026-04-18 |
| [[wiki/etfs/00980d\|00980D — 主動聯博投等入息]] | 聯博投信（外資美商、**第 2 檔主動 ETF、推翻 Round 29「唯一 1 檔」**、Round 37 primary 發現）、**2025-07-24 成立 / 2025-08-04 掛 TPEx（D 字尾真正首檔、早於富邦 00982D）**、**發行價 20 元（首見、非常見 15 元）**、**管理費階梯 0.65/0.60% + 保管費階梯 0.12/0.08%（外資階梯首見、推翻「外資 flat signature」）**、**聯博跨信用等級費率結構分歧：投等階梯 vs 非投等 flat**、**同投信跨 TPEx+TWSE 佈局首見**、**S 智選策略（AB Systematic Fixed Income 量化主動）**、月配、首配 2025-10-21（≈3 個月即首配）、BBB 平均信評、240 檔債券、平均殖利率 6.16%、**淨值 A+B+C 每日揭露 = 本研究最高品質 NAV 揭露**（基本面額 20.00 + 收益平準金 B + 資本損益平準金 C）、保管銀行中國信託、**Round 24 TWSE audit 盲區（TPEx 不含）→ 第 16 種揭露不對稱候選** | active-etf, active-bond-etf, d-suffix, alliancebernstein, foreign-invested, investment-grade-bond, tiered-fee, monthly-dividend, tpex, nav-composition-daily | 2026-04-18 |
| [[wiki/etfs/00986d\|00986D — 主動復華金融債息]] | 復華投信、**2026-03-31 成立（同傘 00998A 同日）**、**櫃 ETF TPEx 第 2 例**、**D 字尾第 4 檔**、34.37 億（3 週、規模爆發力第一）、**管理費階梯 0.60%/0.70% + 保管費 0.06%~0.10%**、**保管銀行台北富邦銀行（與同傘 00998A 合作金庫不同 = Round 30 傘型保管銀行獨立首見）**、全球金融債、黃媛君、復華**第 3 檔主動 ETF 第 3 位獨立經理人**（不複用）、收盤 14.84 元（發行價推定 15 元）、尚未首次配息 | active-etf, active-bond-etf, d-suffix, fuhwa, cross-border, financial-sector-bond, umbrella-fund, otc-etf, tpex, tiered-fee | 2026-04-18 |
| [[wiki/etfs/00993a\|00993A — 主動安聯台灣]] | 安聯投信（外資德系）、**2026-01-20 成立（安聯第 2 檔、A 字尾 Range Gap 最後一檔）**、**125.5 億（3 個月外資爆量、與國泰 127 億齊平）**、**flat 0.70% + flat 0.035%（與姐姐 00984A 完全相同）= 本研究首見「同發行商兩檔主動 ETF 管理費完全相同」**、benchmark **臺灣加權股價指數（績效評量參考、非持股約束）**、施政廷（單人、與 00984A 段俊廷不同）、**連 9 漲 +17.44%（本研究最高單段漲幅未列警示）**、**極簡命名（無策略形容 vs 姐姐嵌「高息成長」）**、**第 6 種同發行商分歧邏輯 = 無分歧**、**Round 36 primary 修正：年配息**（原推測季配）、**同發行商配息頻率分化首見**（00984A 季配 vs 00993A 年配）| active-etf, taiwan-equity, allianz, foreign-invested, flat-fee, benchmark-taiwan-weighted, minimalist-naming, annual-dividend | 2026-04-18 |

> **首批 6 檔（2025-05 到 07）**：00980A 野村優選 / 00982A 群益強棒 / 00981A 統一增長 / 00983A 中信 ARK 創新 / 00984A 安聯高息 / 00985A 野村 50

### Issuers

| Page | Summary | Tags | Last Updated |
|------|---------|------|-------------|
| [[wiki/issuers/uni-president\|統一投信]] | 00981A/00988A 發行商，UPAMC。**2 檔主動 ETF 分歧邏輯 = 地域**（台股 階梯 1.2%/1.0% vs 全球 階梯 1.4%/1.2%，整條 +0.2 pp）、**跨國溢價全在管理費、保管費無平移** | issuer, active-etf | 2026-04-18 |
| [[wiki/issuers/capital-sitc\|群益投信]] | 00982A/00992A/00997A 發行商，Capital SITC。揭露風格「主動警示、配息不拆解」、**3 檔主動 ETF 完成**：00982A 台股全市場 flat 0.8% / 00992A 台股科技 階梯 1.2%-1.0% / 00997A 美股 階梯 1.2%-1.0%（保管費 0.1%-0.12% 為台股 3 倍）、**分歧邏輯 = 主題深度**（非地域/裁量權）、**3 檔 3 位獨立經理人不複用** | issuer, active-etf | 2026-04-18 |
| [[wiki/issuers/allianz\|安聯投信]] | 00984A/00993A 發行商，AGI Taiwan（外資德系）。**2 檔主動 ETF 管理費完全相同 flat 0.70% = 本研究首見同發行商同費率**、**第 6 種同發行商分歧邏輯 = 無分歧**（策略差異不以費率表達）、00993A 3 個月 125.5 億與國泰 127 億齊平（推翻「外資規模弱」觀察）、兩檔經理人不複用（段俊廷 / 施政廷）、兩檔命名策略不一致（嵌「高息成長」vs 極簡）、ETF 配息組成不揭露但共同基金詳細揭露 | issuer, active-etf, foreign-invested, flat-fee-uniform | 2026-04-18 |
| [[wiki/issuers/nomura\|野村投信]] | 00980A/00985A/00999A 發行商，Nomura Asset Management Taiwan（日系外資）。**同發行商內費率水準差反映主動程度**：00980A 0.75% 全主動 vs 00985A 0.45% 增強指數 | issuer, active-etf, foreign-invested, japanese | 2026-04-18 |
| [[wiki/issuers/ctbc-sitc\|中信投信]] | 00981D/00983A/00995A 發行商，CTBC Investments（本土、中信金控）。**Round 41 加入 00981D 後 3 檔結構全部不同**：00983A 美股 4 段階梯 / 00995A 台股 flat / **00981D 美股非投等債 2 段階梯 + 3 段階梯保管費**。**推翻 Round 22 純地域分歧、升維為地域 + 資產類型雙維**（全研究首個雙維分歧投信）。**中信 = 第 2 家跨 TWSE+TPEx 佈局投信**（同聯博、股票 TWSE / 債券 TPEx）。**三段階梯保管費為本研究第二例**（斷點 100/200 億 ≠ 富邦 100/300 億）= 三段非「富邦簽名」、斷點為投信級設計。警告嵌入 ETF 名稱**非全產品一致**（00983A 嵌 vs 00995A 未嵌）——**產品級選擇，非投信文化** | issuer, active-etf, local-sitc, dual-axis-divergence, cross-exchange-issuer | 2026-04-18 |
| [[wiki/issuers/tsit\|台新投信]] | 00986A/00987A 發行商，Taishin SITC（本土、台新新光金）。**非首批、兩檔都 flat、台股 vs 跨國費率差反映地域成本**、**類別錯誤 + 產品主題錯誤為系統性揭露瑕疵**（兩檔都有被動模板誤植）、100% 經理人來自首批挖角 | issuer, active-etf, local-sitc, flat-fee-local, disclosure-error | 2026-04-18 |
| [[wiki/issuers/yuanta\|元大投信]] | 00990A 發行商，Yuanta SITC（**台灣最大本土投信**）。**延後入市**（2025-12-02、晚首批 6–7 個月）、**直接跳過台股切入全球 AI**、**雙 flat 結構**（管理 0.9% + 保管 0.15%）、**跨國主動 ETF 當前最低總負擔**、被動線龐大（00050/00878/00940） | issuer, active-etf, local-sitc, largest-local | 2026-04-18 |
| [[wiki/issuers/fuhwa\|復華投信]] | 00991A/00998A/00986D 發行商，Fuhwa SITC（本土、推定華南金）。**警語嵌名全產品統一（中信後本土第 2 家，跨國/股息版加長）**、**揭露品質高端**（活動頁列 4 維選股策略 + 20 個股舉例）、**同發行商內費率結構不一致：台股 1.0%/0.8% + 0.035% vs 全球 1.2%/1.0% + 0.10%~0.14%**、**分歧邏輯 = 地域（第 3 家地域分歧）**、**傘型基金首見**（復華金融股債雙收傘型、Round 30 完整 ingest）、**傘型保管銀行獨立首見**（00998A 合作金庫 vs 00986D 台北富邦銀行）、每檔獨立經理人不複用（3 檔 3 人） | issuer, active-etf, local-sitc, warning-in-name, umbrella-fund | 2026-04-18 |
| [[wiki/issuers/first-financial-sitc\|第一金投信]] | 00994A 發行商，First Financial SITC（本土、推定第一金控）。**本土 flat 第 4 家且最低（0.70%）**、保管費 0.035% flat、揭露風格中性保守（無特殊主動策略揭露）、官網 fsitc.com.tw eval 失敗（本土第 4 家官網抓取困難）、**低費率+低規模陷阱（24 億）** | issuer, active-etf, local-sitc, taiwan-50-benchmark | 2026-04-18 |
| [[wiki/issuers/cathay\|國泰投信]] | 00400A 發行商，Cathay SITC（本土、國泰金控）。**大型本土投信**（00878 被動 1800+ 億旗艦）、**主動首檔 19 天 107 億規模爆量**、**本土 flat 0.9% 雙例**（元大齊等）、**保管費罕見階梯 0.06%/0.04%**（本土台股唯一非 0.035% flat 且非 00981A 高水準）、**官網 Access Denied（本土第 5 家抓取困難）**、延後入市策略類似元大 | issuer, active-etf, local-sitc, large-local | 2026-04-18 |
| [[wiki/issuers/megabank-itim\|兆豐投信]] | 00996A 發行商，Mega ITIM（**第 11 家投信**、公股兆豐金控、**SITCA A0001 老牌編號**）。首檔主動 2026-03-16 成立、31 億、**flat 0.8%**（本土 flat 0.8% 雙例繼群益 00982A）、**保管銀行元大商業銀行（跨集團首見）**、王仲良、**Yahoo gap discovery 漏網**（Round 24 TWSE primary source audit 才發現） | issuer, active-etf, local-sitc, state-linked | 2026-04-18 |
| [[wiki/issuers/jpmorgan-taiwan\|摩根投信]] | 00989A/00401A 發行商，JPMorgan AM Taiwan（**第 12 家投信**、外資美商）。**跨國在前、台股在後**（與野村/安聯相反）、**外資 flat + 兩檔差 0.15 pp**、**00401A 台股管理費 flat 0.60% 為研究範圍最低**、**經理人架構切換**（跨國單人蓋欣聖 vs 台股核心沈馨+協管魏伯宇）、**Yahoo 經理人欄只揭露核心、遮蔽協管（Round 27 第 14 種揭露不對稱）**、官網 terms-of-use gate + **明文禁止爬蟲**、SITCA A0011、Yahoo 推薦 6 個月未觸 00989A | issuer, active-etf, foreign-invested, us-brand, scraping-restricted | 2026-04-18 |
| [[wiki/issuers/fubon\|富邦投信]] | 00982D/00983D 發行商，Fubon Asset Management（**第 13 家投信**、本土富邦金控、Round 28 首建）。**被動 ETF 線強（00881/0052 等），主動 ETF 2025-09 才進場**。**主動債券 ETF（D 字尾）全研究首見發行者**、**月配息首例**、**三段階梯保管費首見**、**富邦優選收益傘型（傘型第 2 例，繼復華）**、**同傘內分歧邏輯 = 風險等級**（第 5 種同發行商分歧邏輯）、雙經理人不複用（黃詩紋 / 游陳達） | issuer, active-etf, active-bond-etf, fubon, local-sitc, financial-group-linked, umbrella-fund | 2026-04-18 |
| [[wiki/issuers/blackrock-taiwan\|貝萊德投信]] | 00985D 發行商，BlackRock Taiwan（**第 15 家投信**、Round 42 首建）。**全球最大資產管理公司 BlackRock Inc. 台灣分支**（母集團 AUM ~$10 兆 USD）、**iShares 品牌方**（全球最大 ETF 品牌 $3.5 兆 USD）、主動式 ETF 為台灣投信首次發行（過去以境外基金通路）。首檔 00985D 投等債 = **D 字尾管理費最低（0.45%）**、**外資投等 D 字尾保管費結構 100% 同聯博**、**iShares 品牌嵌入基金名稱首見**、成立→上櫃 10 天（D 字尾最短）。規模 9.09 億（1 個月、散戶品牌辨識度低於預期）。地址信義區松仁路 100 號 28 樓 | issuer, active-etf, foreign-invested, us-brand, blackrock, ishares, 15th-sitc, largest-global-am | 2026-04-18 |
| [[wiki/issuers/alliancebernstein\|聯博投信]] | 00980D/00984D 發行商，AllianceBernstein / AB Funds Taiwan（**第 14 家投信**、外資美商）。**Round 37 primary 修正為 2 檔**（非 Round 29 所記「唯一 1 檔」）：**00980D 投等**（2025-07-24、TPEx、階梯費率、S 智選量化）+ **00984D 非投等**（2026-01-22、TWSE、flat、全主動選債）。**第 7 種同發行商分歧邏輯 = 信用等級（非傘型首見）**、**聯博跨信用等級費率結構分歧（階梯 vs flat）= 推翻 Round 29「外資 flat signature」歸納**、**同投信跨 TPEx+TWSE 佈局首見**、**淨值 A+B+C 每日揭露 = 本研究最高品質 NAV 揭露**（00980D）、地址**101 大樓 81 樓（外資最高階）** | issuer, active-etf, active-bond-etf, alliancebernstein, foreign-invested, us-brand, fixed-income-specialist, credit-quality-divergence | 2026-04-18 |

### Mechanisms

| Page | Summary | Tags | Last Updated |
|------|---------|------|-------------|
| [[wiki/mechanisms/active-etf-fee-disclosure\|主動型 ETF 費用揭露]] | TER 揭露不對稱，散戶常低估總成本 | fee, disclosure, active-etf, transparency-gap | 2026-04-18 |
| [[wiki/mechanisms/creation-redemption\|ETF 申贖機制]] | AP 套利如何（失敗）收斂溢折價；主動型的透明度—套利兩難 | creation-redemption, arbitrage, premium-discount, active-etf | 2026-04-18 |
| [[wiki/mechanisms/income-equalization\|收益平準金]] | 主動式 ETF 配息率不錨定指數息率，配息組成未對外揭露 | income-equalization, dividend, disclosure, active-etf | 2026-04-18 |
| [[wiki/mechanisms/active-etf-holdings-disclosure\|主動式 ETF 持股揭露]] | 全透明每日揭露 + T+1 漂移：揭露越多、alpha 越快外流 | holdings-disclosure, full-transparency, arbitrage | 2026-04-18 |
| [[wiki/mechanisms/issuer-voluntary-disclosure\|發行商自主揭露]] | SITCA 只定底線，各投信自律差異大：統一公開配息組成、群益發溢價警告 | voluntary, self-regulation, cross-issuer-gap | 2026-04-18 |
| [[wiki/mechanisms/issuer-divergence-logic\|同發行商內分歧邏輯]] | **Round 39 擴充為 10 家 7 維**（加入聯博「信用等級非傘型」第 7 種、Round 37 衍生）：主題深度（群益）/ 主動裁量權（野村）/ 地域（統一台新中信復華摩根）/ 風險等級傘型（富邦）/ 資產類型傘型（復華）/ 費率無分歧（安聯）/ **信用等級非傘型（聯博、跨結構類型 + 跨交易所）**、**Round 36 新增 Type 6 子分歧：配息頻率分化**（安聯 00984A 季配 vs 00993A 年配）、外資分歧維度最多元（4/10） | divergence-logic, fee-structure, product-line-strategy, cross-issuer-comparison, credit-quality-divergence | 2026-04-18 |
| [[wiki/mechanisms/active-bond-etf-d-suffix\|主動債券 ETF（D 字尾）機制]] | **Round 37 修正為 5 檔**（加入聯博 00980D 真正首檔 2025-07-24、Round 33 原 4 檔漏網 TPEx）：信用品質單調費率光譜（0.55→0.80%）、**月配 5/5 通例 vs A 字尾月配 0**、三段階梯保管費首見（富邦）、傘型子基金保管銀行獨立（復華）、非投等 10.07% 年化殖利率研究最高、**Round 37 新增：外資 flat signature 推翻**（聯博跨信用等級階梯 vs flat 分歧）、**Round 37 新增：淨值 A+B+C 每日揭露**（00980D 唯一、研究最高品質 NAV 揭露）、**Round 37 新增：TPEx audit 盲區**（Round 24 漏 00980D） | active-bond-etf, d-suffix, fixed-income, monthly-dividend, credit-risk, tiered-custody, nav-composition-daily, tpex-blindspot | 2026-04-18 |
| [[wiki/mechanisms/umbrella-fund-active-etf\|傘型基金主動式 ETF]] | 2 例傘型對比：富邦優選收益（00982D+00983D、風險等級軸）vs 復華金融股債雙收（00998A+00986D、資產類型軸）、傘型行政獨立性超乎直覺（保管銀行可不同、配息頻率可不同、費率可不同）、散戶 4 個認知盲點歸納、2 例全為本土投信 | umbrella-fund, twin-funds, custody-independence, sub-fund-divergence | 2026-04-18 |
| [[wiki/mechanisms/monthly-dividend-active-etf\|月配息主動式 ETF]] | 月配主動 ETF 4/4 全 D 字尾（A 字尾 0 檔）、殖利率光譜 6.12–10.07% 與信用風險單調、配息組成揭露缺口（D 字尾發行商未公開 PDF）、5 個散戶漏洞：類年金幻覺/殖利率越高越好陷阱/揭露迫切性/主動裁量配息平滑化/重複除息誤區、配息頻率 × 資產類別光譜圖 | monthly-dividend, d-suffix, income-product, yield-trap, dividend-frequency | 2026-04-18 |

> **Fee disclosure 最新（2026-04-18 round 6–15）**：Round 6 發現第四種揭露不對稱（階梯式 vs flat 第三方壓縮）。Round 7 群益 00992A 確認本土投信 200 億斷點通例。**Round 8 安聯 00984A 推翻「業界通例」**——外資投信採 flat 0.7%，新增**第五種**揭露不對稱（本土階梯 vs 外資 flat）。**Round 9 野村 00980A 強化 flat signature**。**Round 10 中信 00983A 推翻「本土 2 段階梯通例」**——中信採 **4 段階梯**（100/200/300 億三斷點），新增**第六種**揭露不對稱（Yahoo 顯示「最優階梯」當「當前實付」，30 億規模時實付 1.0% 但 Yahoo 顯示 0.7%）。**Round 11 群益 00982A 推翻「同發行商內費率結構一致」**——新增**第七種**揭露不對稱（同發行商內結構不一致）。**Round 12 野村 00985A 完成首批 6 檔 ingest**——發現**第二種同發行商內差異邏輯**：野村用 flat **水準差**（00980A 0.75% 全主動 vs 00985A 0.45% 增強指數），與群益「結構類型差」不同。**00985A 是首批唯一「增強指數型主動 ETF」**（績效指標 Taiwan 50、主動溢價僅 0.13%）。首批 6 檔經理費光譜：**0.45%**（00985A）→ 0.7%（00984A）→ 0.75%（00980A）→ 0.8%（00982A）→ **1.0%+ 加權**（00981A/00983A/00992A）。自律光譜擴展為**六種揭露模式維度**（結果/機制/程序/位置/警告/動態）。**Round 13 台新 00987A 推翻「本土階梯 / 外資 flat」二元假說**——**本土投信採 flat 首例**（0.75%），新增**第八種揭露不對稱**（類別錯誤免責聲明：主動式產品頁使用被動型模板「本基金因採被動式管理方式」）。台新為**揭露品質光譜最低端**，與中信「警告嵌入名稱」最前置揭露形成鮮明對比。**Round 14 台新 00986A 全球龍頭成長**（經理費 1% / 保管費 0.25%）**確認類別錯誤為系統性**揭露模式（兩檔皆有），並新增**第九種揭露不對稱：產品主題錯誤警語**（00986A 警語段寫「追蹤臺灣內需高收益指數」但實為全球股）。**台新同發行商內費率第三種差異邏輯**：投資地域（跨國 vs 台股，跨國溢價 ≈ 0.47%/年）。**Round 15 野村 00999A 高息策略**（尚未掛牌、flat 0.70%）**完成野村 3 檔光譜**（0.45 / 0.70 / 0.75），**推翻 Round 12「主動複雜度」假說**（原預測 ≥1.0%），建立 **Round 15 新假說：野村 flat 費率 = 主動裁量權大小**（裁量約束越小費率越低）。游景德兼任 00980A/00999A。**Round 16 群益 00997A 美國增長**（2026-03-30 成立、階梯 1.2%/1.0%、保管費 0.1%–0.12%）**Round 15「裁量權」假說在群益失效**——美股全主動選股未超過台股科技主題費率，反支持**群益分歧邏輯 = 主題深度**（全市場 flat / 主題+跨國 階梯）。新增**第十種揭露不對稱：同發行商保管費水準差（地域溢價）**——群益台股 0.035% vs 美股 0.1%–0.12% 為 3 倍、台新台股 0.035% vs 全球 0.25% 為 7 倍。**Round 17 統一 00988A 全球創新**（2025-10-21 成立、階梯 1.4%/1.2%、保管費 0.10%–0.12% **無溢價**）**推翻 Round 16「跨國系統性溢價」歸納**——統一台股保管費起徵高（0.10%+），跨國沒有額外溢價。新理解：**Round 16 觀察到的跨國保管費溢價實質是「台股起徵過低（0.035%）造成的視覺落差」**，不是跨國系統性。新增**第十一種揭露不對稱：跨國溢價「放置位置」差異**（統一放管理費 +0.2 pp、群益放保管費、台新兩處都加）。**第三個同發行商內分歧邏輯為「地域」**（統一同台新，不同於群益主題深度/野村裁量權）。**Round 18 元大 00990A AI 新經濟**（2025-12-02 成立、254.17 億、**雙 flat 0.9% + 0.15%**）**元大首檔主動 ETF**、**本土 flat 第 3 家**、**跨國主動 ETF 當前總負擔最低 1.05%**、**策略上直接跳過台股切入全球 AI**（類似台新 00986A 先跨國）、連 4 漲 6.03% 未列警示。**Round 19 復華 00991A 未來 50**（2025-12-09 成立、309.11 億、階梯 1.0%/0.8%、**半年配本研究首見**）**第 8 家投信（復華）**、與 00985A 野村 Taiwan 50 形成「50 主題兩種做法」對比（增強指數 flat 0.45% vs 主動選 150 挑 50 階梯 1.0%/0.8%）、**Round 15 裁量權假說跨投信首次支持**。**Round 19 修正理解：費率設計是多層次結構**（主題選擇/主題內裁量分層/地域溢價位置/同發行商特色），統一歸納只能在同一層內進行。**警語嵌入基金名稱**風格本土第 2 家（繼中信）。揭露品質高品質端（具體選股策略 + 20 個股舉例）。**Round 20 第一金 00994A 台股優**（2025-12-26 成立、24.28 億、**flat 0.70%**）**本土 flat 第 4 家且最低**（第一金 0.70% < 台新 0.75% < 群益 00982A 0.80% < 元大 00990A 0.90%）、**第 9 家投信**、**Taiwan 50 主題三檔子光譜**（00985A 增強 flat 0.45% / 00994A 主動 bench Taiwan 50 flat 0.70% / 00991A 主動選 150 檔 階梯 1.0%/0.8%）。新增**第十二種揭露不對稱：Benchmark 與名稱策略對應模糊**（00994A benchmark Taiwan 50 vs 名稱「趨勢優選」未揭露選股池是否限於 Taiwan 50）。**低規模警訊**：24 億顯示**低費率本身無法吸引規模**、品牌/通路主導。**Round 21 中信 00995A 台灣卓越**（2026-01-13 成立、44.87 億、**flat 0.75%**）**中信同發行商內費率結構不一致**：00983A 美股 4 段階梯 vs 00995A 台股 flat——**中信分歧邏輯 = 地域**（本研究第 4 家確認跨主題用不同結構、第 2 家以地域分歧）。**本土台股 flat 0.75% 雙例**（台新 + 中信），0.75% 可能成「本土台股 flat 標準值」。**Round 19「警語嵌名本土 2 家投信」歸納削弱**：00995A Yahoo 未嵌警語（與 00983A 不同）→ 警語嵌名為**產品級**選擇，非投信級規則。**Round 22 復華 00998A 金融股息**（2026-03-31 成立、28.42 億、**階梯 1.2%/1.0% + 保管 0.10%~0.14%**）**三個新機制首見**：（1）**櫃 ETF（TPEx 而非 TWSE）**、（2）**傘型基金主動式 ETF**（復華金融股債雙收傘型，同傘有 00986D 債息）、（3）**Yahoo 平台截斷使警語嵌名前置失效**。**復華同發行商內費率結構不一致確認**：**分歧邏輯 = 地域**（第 5 家確認跨主題用不同結構、第 3 家以地域分歧、**地域溢價兩處都加三例：台新 + 中信 + 復華**）。**Round 21「警語嵌名削弱」結論反削弱**：復華官網兩檔主動 ETF 都嵌警語（00998A 加長版含「且本基金並無保證收益及配息」），**Yahoo 簡稱為平台截斷**→ Round 19 歸納**恢復效力**。新增**第十三種揭露不對稱：平台簡稱截斷使警語嵌名前置失效**。發現 **00400A 主動國泰動能高息**（第 10 家投信國泰）與 **00986D 主動復華金融債息**（首次觸及主動型債券 ETF 家族）。詳見 [[wiki/mechanisms/active-etf-fee-disclosure]] 和 [[wiki/mechanisms/issuer-voluntary-disclosure]]。

## Open Questions

（累積中，當前是早期階段）

1. **TER 揭露規範**：金管會 / 投信投顧公會對主動型 ETF 的總費用揭露是否強制？格式統一嗎？
2. **溢價持續性**：00981A 月均 0.29% 溢價是單一現象還是整批主動型 ETF 的通病？
3. **「創新能力」 vs 前 300 大 60% 限制**：主動型 ETF 的行銷敘事與法規限制之間的落差普遍嗎？
4. **配息結構**：季配 ETF 的配息中，收益平準金（本金返還）佔比多少？有無強制揭露？（**更新 2026-04-18**：SITCA 函不強制對外揭露，但**統一投信自願公開 00981A 配息組成查詢頁**。實測 00981A 2025-Q4 0.41 元配息 = 100% 可分配淨利益、0% 本金，首次配息未動用平準金——見 [[wiki/mechanisms/income-equalization]]）
5. **規模爆量下的策略變形**：00981A 一個月規模 +45% 後，持股集中度與週轉率如何變化？
6. **成交量 #1 的意義**：00981A 單日成交 128 億（超越 0050）是散戶熱度還是 AP 頻繁套利？自然人 vs 法人比例？
