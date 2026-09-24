| 日期             | 事件／命名變化                                                                                                                                                                           | 證據狀態                                       | 引用                                                     |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------- |
| 2026-01-19       | 在層級體系中出現 devSCR（DBG → DCL → AISCR → devSCR），作為後續規則／約束工作的前身脈絡                                                                                                  | 對話紀錄（有日期）                             | [1]                                                      |
| 2026-01-20–01-23 | 檢查 devSCR 是否仍需 NNL/CNL 與 Rule/Ruleset；為 NNL/CNL 的最早可查對話時窗                                                                                                              | 對話紀錄（有日期）                             | [1]                                                      |
| 日期未確認       | v0.1 — devSCR 初始：Rule 主要被定義為 Constraint；CNL 作為唯一規範語言                                                                                                                   | 版本條目（未標日期）；時間由相鄰里程碑括限     | [2]（括限：2026-01-20–23 [1]；≤2026-03-16 [4]）          |
| 日期未確認       | v0.2 — Rule/Ruleset 結構化；建立 Rule Library 概念                                                                                                                                       | 版本條目（未標日期）                           | [2]（括限：≥2026-01-20–23 [1]）                          |
| 日期未確認       | v0.3 — 引入語言層：NNL 與 CNL；首次區分 Intent Optimization（NNL）與 Behavior Constraint（CNL）                                                                                          | 版本條目（未標日期）                           | [2]（括限：2026-01-20–23 已討論 NNL/CNL [1]）            |
| 2026-01-30       | DCL 重新定位為 DEA；DCL 中的規則與約束內容後續被 BRA／Boundary／Scope 吸收                                                                                                               | 對話紀錄（有日期）                             | [1]                                                      |
| 日期未確認       | v0.4 — 初步形成 BRA；建立 NNL → CNL → Rule → Ruleset 的管線                                                                                                                              | 版本條目（未標日期）                           | [2]（括限：≤2026-03-16 [1][4]）                          |
| 日期未確認       | v0.6 — 語義精煉：Policy（MUST）與 Constraint（MUST NOT）分離；提出 Minimal Constraint Principle                                                                                          | 版本條目（未標日期）                           | [2]（括限：≤2026-03-16，該日對話明確回顧此關鍵演進 [4]） |
| 日期未確認       | v0.7 — 語言統一：以 RNL（Rule Normative Language）取代 CNL；形成 NNL（Prompt）/ RNL（Rule）二層                                                                                          | 版本條目（未標日期）                           | [2]（括限：≤2026-03-16，該日對話使用 NNL/RNL 二分 [4]）  |
| 2026-03-16       | 規則／constraint／ruleset 收束為 BRA 的正式架構名稱；同日對話確立四層（Language: NNL/RNL；Rule；Governance Asset；Execution 外部）與 MUST/MUST NOT 的術語分離                            | 對話紀錄（有日期）；總結敘述明確指認命名與結構 | [1], [4]                                                 |
| 日期未確認       | v1.0 — BRA 完整框架：語言層（NNL/RNL）、規則結構、治理資產層（Rule Library/Ruleset）、與外部執行層的邊界；原則含「每個 Ruleset 至少含一個 Constraint」與 BRA 對 Boundary/VSS/AA 的獨立性 | 版本條目（未標日期）                           | [2]（括限：≥2026-03-16 [4]）                             |
| 2026-09-16       | 回顧「What Is a Rule?」：說明規則概念源自軟體開發情境、從指令抽離到可重用規則／ruleset 的過程與再詮釋問題                                                                                | 敘述性回顧（有日期），非命名事件               | [3]                                                      |

來源與日期說明
- [1] chat/Theory.md（源檔未編碼日期；內含依訊息 created_at 重建的時間線）。提供帶日期的對話事件：2026-01-19（devSCR 於分層體系中）、2026-01-20–23（NNL/CNL 與 Rule/Ruleset 的檢查）、2026-01-30（DCL → DEA 重新定位）、2026-03-16（規則／constraint／ruleset 收束為 BRA 定名）。
- [2] articles/papers/history/2026-03_behavior-rule-architecture.history.md（版本史檔；各 v0.x／v1.0 無個別日期標註）。因此所有 v0.x／v1.0 條目皆標為「日期未確認」，並以 [1]、[4] 的具日證據作為括限：
  - 下限括限：2026-01-20–23 已有 NNL/CNL 與 Rule/Ruleset 的對話檔案 [1]。
  - 上限括限：2026-03-16 對話已採用 NNL/RNL、並回顧 MUST/MUST NOT 的語義分離 [4]，且同日時間線指認 BRA 收束定名 [1]。
- [3] chat/gemini/.../2026-09-16_...（2026-09-16）。提供對「規則」定義與來源脈絡的事後敘述，非命名首次出現的證據。
- [4] chat/claude/.../2026-03-16_...（對話 session created_at：2026-03-16 Asia/Taipei）。總結明確記載三項關鍵演進：早期以 Constraint 作為統一稱呼；後分離為 Policy（MUST）/Constraint（MUST NOT）；語言層採 NNL（Prompt）/RNL（Rule）並形成四層結構。

仍待補強的日期缺口
- 「Rule 主要被定義為 Constraint」（v0.1）、「引入 NNL/CNL 的語言層」（v0.3）、「初步形成 BRA」（v0.4）、「Policy/Constraint 分離」（v0.6）與「RNL 取代 CNL」（v0.7）等版本節點在 [2] 中均未標示確切日期；僅能以 2026-01-20–23（NNL/CNL 已在對話中被檢視）與 2026-03-16（BRA 架構與 NNL/RNL 已被確認）作為括限。
- NNL、CNL 的「最早出現」：目前可驗證的最早帶日期對話證據為 2026-01-20–23 的 devSCR 討論 [1]；若需更早首次提及，尚缺更早期之對話訊息或文檔。
- 「Constraint 作為規則定義」的首次提及日期：僅見於未標日期的版本史條目 [2]；缺乏具日對話或提交紀錄以標定首現時間。
[1] chat · chat/Theory.md
[2] history · articles/papers/history/2026-03_behavior-rule-architecture.history.md
[3] chat · chat/gemini/conversations/2026/2026-09/2026-09-16_114640__翻譯__08cdf6d4b33bd82a.md
[4] chat · chat/claude/conversations/2026/2026-03/2026-03-16_145043__BRA & BCM__5f686abf-e001-49b9-b2bb-2dd62f7173c2.md
[5] chat · chat/gemini/attachment-index.csv
[6] document · articles/engineering-decision-behavior-notes/raw/behavior-rule-architecture/0_Gemini-01.md
[7] chat · chat/grok/conversations/2026/2026-03/2026-03-16_145000__BRA & BCM__1cca3e07-6f34-43f1-b277-7d6b9e76ca33.md
[8] chat · chat/gemini/conversations/2026/2026-03/2026-03-16_144935__評價 BRA 是否具備變成論文價值__3fc1dbf06fc4d688.md