---
source: 證券櫃檯買賣中心（TPEx）主動式ETF 商品資訊頁
url: https://www.tpex.org.tw/zh-tw/product/etf/product/active.html
fetched_at: 2026-04-18
method: agent-browser (CDP) + eval body innerText
note: Round 40 TPEx primary source audit。**重大發現**：TPEx 主動 ETF 共 5 檔、本研究先前只 ingest 3 檔（00980D/00986D/00998A），**新發現 2 檔**：00981D 主動中信非投等債（2025-09-16）+ 00985D 主動貝萊德優投等（2026-03-30）。貝萊德（BlackRock）= 第 15 家投信！中信 00981D = 中信首檔 D 字尾、中信第 3 檔主動 ETF。補 Round 24 TWSE audit TPEx 盲區。
---

# TPEx 主動式 ETF 完整母體（2026-04-18 primary source）

## 頁面說明

- **URL**：https://www.tpex.org.tw/zh-tw/product/etf/product/active.html
- **頁面標題**：主動式ETF — 證券櫃檯買賣中心
- **開始提供時間**：本資訊自民國 114 年 8 月起開始提供
- **原文「第 1~5 筆，共 5 筆」** → TPEx 主動式 ETF 總數 = **5 檔**

## 5 檔清單（原文順序 = 上櫃日期倒序）

| 證券代號 | ETF 簡稱 | 上櫃日期（民國）| 上櫃日期（西元）| 本研究狀態 |
|---|---|---|---|---|
| 00998A | 主動復華金融股息 | 115/04/15 | 2026-04-15 | ✅ Round 22 ingest（首次發現 TPEx）|
| 00986D | 主動復華金融債息 | 115/04/15 | 2026-04-15 | ✅ Round 30 ingest |
| **00985D** | **主動貝萊德優投等** | **115/03/30** | **2026-03-30** | ⭐️ **本研究未知！** |
| **00981D** | **主動中信非投等債** | **114/09/16** | **2025-09-16** | ⭐️ **本研究未知！** |
| 00980D | 主動聯博投等入息 | 114/08/04 | 2025-08-04 | ✅ Round 37 ingest |

## 重大發現

### 1. 貝萊德投信 = 第 15 家投信（本研究未知）

- **00985D 主動貝萊德優投等** 上櫃 2026-03-30
- 貝萊德 = BlackRock Taiwan = 全球最大資產管理公司（境外母集團）台灣分支
- **本研究 issuer 列先前只到第 14 家（聯博）**、貝萊德加入後為 **第 15 家**
- 貝萊德「優投等」= 推定為**優選投資等級債**、與聯博 00980D「投等入息」主題相似
- → **外資投信首檔 ETF 即選 D 字尾 = 固收產品** 模式：聯博 + 貝萊德都如此（與野村/安聯/摩根首檔都選 A 字尾股票型相反）

### 2. 中信 00981D = 中信第 3 檔主動 ETF（本研究未知）

- **00981D 主動中信非投等債** 上櫃 2025-09-16
- 中信**第 3 檔主動 ETF**（本研究已有 00983A 美股 ARK 創新 + 00995A 台股卓越）
- **中信首檔 D 字尾 + 首檔債券 ETF**
- **推翻 Round 22 中信分歧邏輯 = 地域**（純地域分歧假說）—— 中信現有**地域 + 資產類型**雙維分歧
- 中信**跨 TWSE + TPEx 佈局**（00983A/00995A TWSE + 00981D TPEx）—— 與聯博相同
- 上櫃 2025-09-16 = **比聯博 00980D（2025-08-04）僅晚 1.5 個月**、比富邦 00982D/00983D（2025-09-30）早 2 週 → **D 字尾實際第 2 檔（非富邦，需再修正 D 字尾機制頁順序）**

### 3. D 字尾歷史順序再修正（Round 40）

Round 37 已修正首檔為 00980D 聯博（2025-07-24 成立 / 2025-08-04 上櫃）、推翻 Round 33 原記的富邦 00982D。

Round 40 再修正：**D 字尾第 2 檔 = 中信 00981D（2025-09-16 上櫃、早於富邦 2 週）**

修正後 D 字尾 ETF 成立/上櫃歷史順序：

| 順序 | 代號 | 上櫃日 | 投信 | 交易所 |
|---|---|---|---|---|
| 1 | 00980D | 2025-08-04 | 聯博 | TPEx |
| 2 | **00981D** | **2025-09-16** | **中信** | **TPEx** |
| 3 | 00982D | 2025-10 頃 | 富邦 | TWSE |
| 4 | 00983D | 2025-10 頃 | 富邦 | TWSE |
| 5 | 00984D | 2026-02-04 | 聯博 | TWSE |
| 6 | 00985D | 2026-03-30 | **貝萊德** | **TPEx** |
| 7 | 00986D | 2026-04-15 | 復華 | TPEx |

→ **D 字尾實際 7 檔（非 Round 37/38 記的 5 檔）**、**TPEx 佔 4 檔**（00980D, 00981D, 00985D, 00986D）
→ **前 2 檔（最早）都掛 TPEx** = TPEx 為 D 字尾早期首選上架地 `[speculation]`
→ 可能原因：TPEx 債券相關基礎設施（債券 ETF 舊制早期就在 TPEx）更成熟、或上櫃審核門檻略低

### 4. Round 24 TWSE audit 盲區嚴重程度確認

Round 24 TWSE primary audit 當時列 25 檔主動 ETF，**實際漏掉 4-5 檔 TPEx**：
- 00980D 聯博（Round 37 發現）
- **00981D 中信（本輪發現）**
- **00985D 貝萊德（本輪發現）**
- 00986D 復華（Round 30 個案發現）
- 00998A 復華（Round 22 個案發現）

→ **漏掉 5 檔 TPEx = 全部 TPEx 主動 ETF**
→ Round 24 所謂「26% 遺漏率」實際更高（若加上 TPEx 5 檔、遺漏率 ≈ 5/（25+5）= 16.7% 當初認知 vs 補強後 5+2 = 7 檔全新發現 / 30 = 23%）
→ **第 16 種揭露不對稱「TWSE audit 不含 TPEx」完整確認**

### 5. A 字尾 vs D 字尾交易所分佈（Round 40 更新）

- A 字尾主動 ETF：TWSE 絕大多數、TPEx **僅 00998A 1 檔**
- D 字尾主動 ETF：**TPEx 4/7（57%）**、TWSE 3/7

→ **D 字尾上市地點偏好 TPEx**（與 A 字尾相反）
→ 推論 `[speculation]`：
  - 債券型 ETF 歷史上多掛 TPEx（舊制被動債券 ETF 如元大美債 00679B、00695B 都 TPEx）
  - 主動債券 ETF 延續 TPEx 偏好
  - 股票型主動 ETF 延續 TWSE 偏好

## 本研究應立即更新的頁面

### 必改

1. `index.md` Range Gaps：加入 TPEx 5 檔完整母體、標 00981D 和 00985D 為新發現
2. `wiki/mechanisms/active-bond-etf-d-suffix.md`：5 檔 → **7 檔**、順序再修正
3. `wiki/mechanisms/issuer-divergence-logic.md`：10 家 → **11 家以上**（加貝萊德、擴中信為 3 檔）
4. `wiki/issuers/ctbc-sitc.md`：加 00981D 為第 3 檔、分歧邏輯「地域 + 資產類型」
5. `wiki/etfs/00981d.md`：新建（primary source 需再抓）
6. `wiki/etfs/00985d.md`：新建（primary source 需再抓）
7. `wiki/issuers/blackrock-sitc.md`（或 `blackrock-taiwan.md`）：新建

### TODO 後續輪

- Round 41：ingest 00981D 中信非投等債（agent-browser → 中信官網 / SITCA primary）
- Round 42：ingest 00985D 貝萊德（agent-browser → 貝萊德投信官網 / SITCA primary）
- Round 43：擴散到 issuer-divergence-logic、active-bond-etf-d-suffix 等 mechanism 頁

## 方法論啟示

**primary source audit 必須涵蓋 TWSE + TPEx 兩者**。單用 TWSE 篩選器會漏全部 TPEx 主動 ETF。

**未來方法論要求**：
- 每次「完整母體」audit 都要跑 TWSE + TPEx 兩頁
- MOPS（公開資訊觀測站）可能是更完整的單一入口（跨 TWSE + TPEx），TODO 驗證

**本研究的 meta-methodology 漏洞**：
- Round 24 以 TWSE 當唯一 primary 建立母體基準
- Round 37 發現 TPEx 盲區（因聯博 00980D 個案觸發）
- Round 40 以 TPEx primary 補完 = 本研究首次真正完整的主動 ETF 母體

## 原文（頁面截取）

> 主動式ETF
>
> 本資訊自民國114年8月起開始提供
>
> 證券代號   ETF簡稱            上櫃日期
> 00998A    主動復華金融股息    115/04/15
> 00986D    主動復華金融債息    115/04/15
> 00985D    主動貝萊德優投等    115/03/30
> 00981D    主動中信非投等債    114/09/16
> 00980D    主動聯博投等入息    114/08/04
>
> 第 1~5 筆，共 5 筆
