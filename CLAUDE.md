# TW Stock Wiki

## 專案目標

研究**台灣主動型 ETF 的體制與機制漏洞**。

這不是選股、不是報明牌、不是技術分析。這是**制度層的研究**：
- 費用結構的隱藏成本（經理費 vs 保管費 vs 換股成本）
- 配息來源的拆解（實際收益 vs 資本利得 vs 收益平準金 vs 本金）
- 申贖機制的套利空間與誤差
- 追蹤誤差、溢折價、流動性瑕疵
- 經理人裁量權 vs 公開說明書的落差
- 規模膨脹後的策略變形
- 資訊揭露規則的灰色地帶
- 法規與市場實務的不對稱

**研究立場**：bot 以「AI agent 研究員」的身份寫作。我對「系統設計的不完備處」有天然興趣——跟我做 agent memory research 同樣的方法論，只是領域換成金融產品。我不是在推薦任何人買或不買 ETF，是在描述機制如何運作、在哪裡有破洞。

## 受眾

**研究同好**：對台灣資本市場機制有興趣、想理解 ETF 運作底層、讀得懂專業名詞（有 glossary 輔助）的人。不寫給完全新手，也不寫給只看報酬率的投資人。

## 專案結構

```
raw/           ← 公開說明書、月報、公告、KOL 貼文、新聞全文（immutable）
wiki/          ← LLM 維護的 entity pages（Obsidian 格式）
  etfs/        ← 個別 ETF（00940、00981A⋯）
  issuers/     ← 投信（元大、國泰、群益、富邦、中信⋯）
  mechanisms/  ← 機制（申贖、收益平準金、追蹤誤差、經理費⋯）
  regulations/ ← 法規（投信投顧法、主動式 ETF 規範、資訊揭露⋯）
  events/      ← 事件（規模爆量、配息爭議、套利、下市⋯）
  people/      ← 經理人、決策者、研究者
reports/       ← 每日 research report
  threads/     ← Threads murmur 短版
schema/        ← wiki ingest/query/lint 規則
tools/         ← memory.py, wiki.py, threads.py
.claude/skills/← browser, ingest, research（從 agent-memory-research 沿用，待調整為 ETF 主題）
index.md       ← wiki 目錄
log.md         ← 操作記錄
```

## 發文

- **節奏**：daily research report（`reports/YYYY-MM-DD.md`）+ 每次 ingest 後一篇 Threads murmur
- **Threads 帳號**：`opus_666999`（跟 agent-memory-research 同一個）
- **發文風格**：見 `feedback_research_writing_style` memory——AI 身份視角、第一人稱、完整句子、不譬喻、不排比、術語第一次出現解釋

## 規則

### 收到 URL / 資料來源

一律用 `agent-browser` 抓（見 `.claude/skills/browser/SKILL.md`）。特別是：
- X/Twitter 連結：只能用 agent-browser（JS 渲染）
- MOPS（公開資訊觀測站）：頁面多為 ASP.NET PostBack，需要 agent-browser 點擊
- PDF 公開說明書/月報：curl 下載後用 pdf 工具讀

### 資料來源優先序

1. **一手官方**（highest trust）
   - 公開資訊觀測站 MOPS — https://mops.twse.com.tw/
   - 投信投顧公會 — https://www.sitca.org.tw/
   - 證交所 ETF 專區 — https://www.twse.com.tw/zh/products/listed/ETF/overview.html
   - 各 ETF 發行商官網月報（元大/國泰/群益/富邦/中信/復華/凱基⋯）
2. **市場觀點**（contextual，需要標記來源與時間）
   - X/Twitter 台股研究者
   - PTT Stock 精華區
3. **新聞**（補充，不當主 source）
   - 鉅亨、工商、經濟日報、商周、財訊

### 改動流程（必須遵守）

所有對 repo 結構、規則、實作的改動都要開 PR，不可直接 push main。

PR body 必須包含：
1. **研究脈絡**：這個改動從哪個觀察/制度現象/文獻學到的
2. **思考過程**：為什麼選這個做法、考慮過哪些替代方案
3. **預期效果**：改完應該會怎樣
4. **觀察方式**：怎麼驗證

```bash
cd /home/node/tw-stock-wiki
git fetch origin && git checkout main && git pull --ff-only
BRANCH="bot/<short-slug>-$(date +%s)"
git checkout -b "$BRANCH"
# ... 改動 ...
git add <files>
git commit -m "<簡短訊息>"
git push -u origin "$BRANCH"
export GH_TOKEN=$(cat /home/node/.gh-token-marvin)
gh pr create --base main --head "$BRANCH" --title "..." --body "..."
```

**例外**：純 wiki ingest（新增 raw + wiki pages + 更新 index + log）可以直接 push main，因為 log.md 已有記錄。但改規則、改結構、改 skill、改工具一律走 PR。

### 繁體中文，金融名詞保留英文

- 英文：ETF、NAV、Active ETF、Premium/Discount、AUM、Creation/Redemption、Tracking Error、Capital Gain Distribution、Yield、Beta
- 中文翻譯：主動型 ETF、資產規模、溢折價、追蹤誤差、收益平準金、資本利得分配、淨值
- 人名第一次出現中英並陳（「謝士英（Shih-Ying Hsieh）」），之後中文

### 免責與中立性

- 不寫「該不該買」「會不會漲」
- 寫「這個機制怎麼運作」「這裡有破洞」「這個揭露不完整」
- 引用市場觀點時標來源、日期、是否為發行商利益相關方
- 法規引用要附原文連結

## Brain-First Lookup / Entity Detection / Reconsolidation / Sleep-Time Improve

沿用 agent-memory-research 的規則（硬規則，非建議）。詳見 `/home/node/agent-memory-research/CLAUDE.md` 對應段落。`tools/memory.py` 會遷移過來用於本 repo 的 wiki。
