# TW Stock Wiki — Index

> Auto-maintained by LLM. Do not edit manually.

研究主題：**台灣主動型 ETF 的體制與機制漏洞**。

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

> **首批 6 檔（2025-05 到 07）**：00980A 野村優選 / 00982A 群益強棒 / 00981A 統一增長 / 00983A 中信 ARK 創新 / 00984A 安聯高息 / 00985A 野村 50

### Issuers

| Page | Summary | Tags | Last Updated |
|------|---------|------|-------------|
| [[wiki/issuers/uni-president\|統一投信]] | 00981A 發行商，UPAMC | issuer, active-etf | 2026-04-18 |
| [[wiki/issuers/capital-sitc\|群益投信]] | 00992A/00982A/00997A 發行商，Capital SITC。揭露風格「主動警示、配息不拆解」 | issuer, active-etf | 2026-04-18 |
| [[wiki/issuers/allianz\|安聯投信]] | 00984A/00993A 發行商，AGI Taiwan（外資）。費率 flat 0.7%，ETF 配息組成不揭露 | issuer, active-etf, foreign-invested | 2026-04-18 |
| [[wiki/issuers/nomura\|野村投信]] | 00980A/00985A/00999A 發行商，Nomura Asset Management Taiwan（日系外資）。費率 flat 0.75%，主動型 ETF 連發 3 檔最多 | issuer, active-etf, foreign-invested, japanese | 2026-04-18 |

### Mechanisms

| Page | Summary | Tags | Last Updated |
|------|---------|------|-------------|
| [[wiki/mechanisms/active-etf-fee-disclosure\|主動型 ETF 費用揭露]] | TER 揭露不對稱，散戶常低估總成本 | fee, disclosure, active-etf, transparency-gap | 2026-04-18 |
| [[wiki/mechanisms/creation-redemption\|ETF 申贖機制]] | AP 套利如何（失敗）收斂溢折價；主動型的透明度—套利兩難 | creation-redemption, arbitrage, premium-discount, active-etf | 2026-04-18 |
| [[wiki/mechanisms/income-equalization\|收益平準金]] | 主動式 ETF 配息率不錨定指數息率，配息組成未對外揭露 | income-equalization, dividend, disclosure, active-etf | 2026-04-18 |
| [[wiki/mechanisms/active-etf-holdings-disclosure\|主動式 ETF 持股揭露]] | 全透明每日揭露 + T+1 漂移：揭露越多、alpha 越快外流 | holdings-disclosure, full-transparency, arbitrage | 2026-04-18 |
| [[wiki/mechanisms/issuer-voluntary-disclosure\|發行商自主揭露]] | SITCA 只定底線，各投信自律差異大：統一公開配息組成、群益發溢價警告 | voluntary, self-regulation, cross-issuer-gap | 2026-04-18 |

> **Fee disclosure 最新（2026-04-18 round 6–9）**：Round 6 發現第四種揭露不對稱（階梯式 vs flat 第三方壓縮）。Round 7 群益 00992A 確認本土投信 200 億斷點通例。**Round 8 安聯 00984A 推翻「業界通例」**——外資投信採 flat 0.7%，新增**第五種**揭露不對稱（本土階梯 vs 外資 flat）。**Round 9 野村 00980A 強化 flat signature**——德/日兩家外資共同指向 flat 模型，且 **4 家首批投信中 3 家不揭露配息組成**（群益、安聯、野村），只有統一揭露。詳見 [[wiki/mechanisms/active-etf-fee-disclosure]] 和 [[wiki/mechanisms/issuer-voluntary-disclosure]]。

## Open Questions

（累積中，當前是早期階段）

1. **TER 揭露規範**：金管會 / 投信投顧公會對主動型 ETF 的總費用揭露是否強制？格式統一嗎？
2. **溢價持續性**：00981A 月均 0.29% 溢價是單一現象還是整批主動型 ETF 的通病？
3. **「創新能力」 vs 前 300 大 60% 限制**：主動型 ETF 的行銷敘事與法規限制之間的落差普遍嗎？
4. **配息結構**：季配 ETF 的配息中，收益平準金（本金返還）佔比多少？有無強制揭露？（**更新 2026-04-18**：SITCA 函不強制對外揭露，但**統一投信自願公開 00981A 配息組成查詢頁**。實測 00981A 2025-Q4 0.41 元配息 = 100% 可分配淨利益、0% 本金，首次配息未動用平準金——見 [[wiki/mechanisms/income-equalization]]）
5. **規模爆量下的策略變形**：00981A 一個月規模 +45% 後，持股集中度與週轉率如何變化？
6. **成交量 #1 的意義**：00981A 單日成交 128 億（超越 0050）是散戶熱度還是 AP 頻繁套利？自然人 vs 法人比例？
