# [Articles] X

**Created:** 2026/9/22 9:50:53 PM  
**Updated:** 2026/9/23 12:38:10 PM  
**Exported:** 2026/9/23 12:45:16 PM  
**Link:** [https://chatgpt.com/g/g-p-6a922ef663e4819196f7a02f06d38277-social/c/6ab287bb-d218-83ee-92f1-9f3ead530421](https://chatgpt.com/g/g-p-6a922ef663e4819196f7a02f06d38277-social/c/6ab287bb-d218-83ee-92f1-9f3ead530421)  

## Prompt:
2026/9/22 下午9:52:12

我需要一篇 X Articles，大約說明一下 程式測試/軟體測試 QA 的歷史，從最早的驗收項目，到最新的 AI 測試驗收，從單元到 E2E，包含文件/工具/方法

## Response:
2026/9/22 下午9:52:24

我會把這篇寫成「測試不是突然從 Unit Test 開始，而是從驗收條件一路工程化到今天的 AI 驗收」這條歷史線，並把每一階段常見的文件、方法與工具放進同一個脈絡。最後一段我會把傳統軟體測試與 AI/Agent 驗收分開，避免把兩種測試混成同一件事。

目前比較清楚的一條演化線是：1950s「測試≈除錯」→ 1957 後測試開始被視為獨立活動 → 1980s 測試文件正式標準化 → 1990s–2000s xUnit、TDD、BDD、CI 與瀏覽器自動化把測試搬進開發流程 → 2010s 微服務與 E2E/contract testing 擴大驗證邊界 → 2020s 開始面對「結果不再完全 deterministic」的 AI/Agent eval。IEEE 829 在 1983 年已正式定義 software test documentation；今天 ISO/IEC/IEEE 29119 則把 process、documentation、technique 分開成一整套測試體系。

> **規劃文章脈絡**
>
> 我會撰寫一篇適合 X Article 的完整歷史脈絡，從早期驗收清單、測試文件與品質保證，延伸到單元測試、整合測試、E2E、CI/CD，以及現代 AI 系統的評測與驗收方法。
>
> **規劃文章脈絡**
>
> 
>
> **建構歷史脈絡**
>
> 我會補足早期驗收、正式測試流程、V 模型、TDD、敏捷、CI/CD、測試金字塔、契約測試與現代 AI 評測，並區分軟體測試與 AI 系統行為驗收。
>
> **建構歷史脈絡**
>
> 
>
> **已搜尋 6 個網站**
>
> 
>
> 處理時間為 1m 37s

這篇比較適合用「驗收邊界不斷擴大」來寫，而不是單純羅列 Unit / Integration / E2E。這樣可以把 QA、文件、工具、方法以及今天的 AI Eval 串成同一條工程演化線。

**social_post: **

# 從驗收清單到 AI Evals：軟體測試七十年的演化

很多人談軟體測試時，第一個想到的是 Unit Test。

JUnit、pytest、Jest。

再往上一層是 Integration Test、API Test，最後是 Selenium、Cypress、Playwright 做 End-to-End Test。

但軟體測試並不是從 Unit Test 開始的。

如果把時間往前拉七十年，軟體測試最早面對的問題其實非常直接：

**這套東西到底有沒有做到原本要求它做的事情？**

換句話說，最早的問題比較接近「驗收」，而不是今天我們熟悉的「測試框架」。

而軟體測試接下來七十年的發展，可以看成一個驗證範圍不斷擴張、驗證證據不斷結構化，最後逐漸自動化的過程。

---

## 一開始，Testing 和 Debugging 幾乎是同一件事

早期程式規模很小。

程式設計師寫完程式、執行、看到錯誤、修改，再重新執行。

今天我們會把這些活動拆成：

Development  
Debugging  
Testing  
Verification  
Validation  
Acceptance

但在早期，它們並沒有如此清楚的邊界。

1957 年，Charles L. Baker 在評論 Daniel McCracken 的《Digital Computer Programming》時，明確區分了 program testing 與 debugging，這通常被視為軟體測試逐漸成為獨立活動的重要歷史節點。([測試參考網站](https://www.testingreferences.com/testinghistory.php?utm_source=chatgpt.com))

這時候的「測試文件」也不像今天有 Test Case Management System。

真正重要的可能只是：

需求是什麼？

輸入什麼？

應該得到什麼結果？

實際得到什麼？

能不能接受？

因此，最原始的測試其實已經包含今天仍然存在的核心結構：

**Input → Execution → Expected Result → Actual Result → Acceptance**

工具變了，但這個基本模型幾乎沒有消失。

---

## 從「把 Bug 找出來」走向 Verification

到了 1960s、1970s，軟體規模開始變大。

測試逐漸不再只是程式設計師自己執行幾個案例，而開始形成獨立活動。

Black-box testing、white-box testing、functional testing、system testing，以及 verification / validation 的概念逐漸被工程化。

這個階段也留下了一個非常重要的觀念。

Edsger Dijkstra 在 1970 年代指出：

> Program testing can be used to show the presence of bugs, but never to show their absence.

也就是說：

**測試通過，不等於軟體被證明「沒有錯」。**

它只代表在已經定義並執行的測試條件下，沒有觀察到預期要偵測的錯誤。([德州大學奧斯丁分校計算機科學系](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD268.html?utm_source=chatgpt.com))

這個觀念直到今天仍然非常重要。

100% Unit Test Pass 不代表系統正確。

E2E Pass 也不代表所有使用情境都正確。

到了 AI，更不可能因為 Benchmark 得到某個分數，就宣稱系統「已被證明可靠」。

Testing 從來都不是絕對正確性的證明。

它是一種**累積工程信心的方式**。

---

## 1980s：測試開始擁有正式文件體系

1983 年，IEEE 發布 IEEE 829 Software Test Documentation。

這是一個很值得注意的歷史節點。

因為 Testing 不再只是「執行一些 test cases」，而開始有一套正式的證據結構，例如：

Test Plan  
Test Design Specification  
Test Case Specification  
Test Procedure Specification  
Test Log  
Incident Report  
Test Summary Report

IEEE 829 並沒有規定你一定要使用哪一種測試方法或工具，而是在定義：

**一個可以被管理、重複、檢查與稽核的測試活動，應留下什麼資訊。** ([IEEE Standards Association](https://standards.ieee.org/ieee/829/1217/?utm_source=chatgpt.com))

這其實也是 QA 與單純 Testing 開始明顯分化的地方。

Testing 比較偏向：

「這個系統在某個條件下是否產生預期結果？」

而 Quality Assurance 涵蓋的範圍更大：

需求是否清楚？

測試是否完整？

流程是否遵循標準？

缺陷是否被追蹤？

變更是否重新驗證？

結果是否具有證據？

換句話說：

**Test 是活動，QA 開始變成一套品質控制系統。**

今天 IEEE 829 已經被新的標準體系取代。ISO/IEC/IEEE 29119 將 software testing 分成 general concepts、test processes、test documentation、test techniques 等不同部分，而不是只定義一份 Test Plan 或 Test Case 長什麼樣子。([ISO](https://committee.iso.org/sites/jtc1sc7/home/projects/flagship-standards/isoiecieee-29119-series.html?utm_source=chatgpt.com))

---

## 1990s：Unit Test 把測試往程式碼旁邊拉

接下來發生了一個很重要的轉變。

以前測試經常位於 development 後面。

Developer：

「程式寫好了。」

然後交給 QA：

「請開始測試。」

1990s 的 Extreme Programming、xUnit framework，以及後來的 JUnit，開始改變這個關係。

Kent Beck 與 Erich Gamma 建立的 JUnit 在 1990 年代末對 Java 社群產生很大影響，並帶動不同語言的 xUnit framework。([martinfowler.com](https://martinfowler.com/articles/continuousIntegration.html?utm_source=chatgpt.com))

測試開始變成程式碼本身的一部分。

Developer 寫：

```text
function
```

旁邊也寫：

```text
test_function
```

於是 Test 不再只有：

「整套系統完成後，它能不能運作？」

而多了一個新的驗證層：

「這一個 class、function、module 的行為是否符合預期？」

Unit Test 的價值不只是找到 Bug。

更重要的是它降低了驗證成本。

如果一個系統有 10,000 個行為，不必每次修改一行程式，就重新由人把整套系統操作一次。

很多局部行為可以透過 machine-executable assertions 快速重新驗證。

---

## TDD：測試甚至跑到了程式碼前面

Test-Driven Development 又向前走了一步。

傳統順序是：

Code → Test

TDD 則將流程變成：

Test → Code → Refactor

這是一個很大的觀念轉換。

Test 不再只是驗證 implementation。

它也可以先表達：

**implementation 應該滿足什麼行為。**

於是測試開始同時具有兩種角色：

Verification artifact

以及

Executable specification

這也是後來 BDD 能夠出現的重要背景。

---

## 2000s：Acceptance Criteria 開始變成可以執行的語言

Agile 出現後，軟體開發週期縮短。

如果幾個月才進行一次完整 QA，已經跟不上幾天甚至每天一次的軟體變更。

因此測試開始進一步被搬進 development workflow。

2000 年前後 Continuous Integration 的實踐逐漸成形：自動 build、自動執行 test suite，只要 integration 發生，就重新驗證軟體。Martin Fowler 早期對 CI 的描述就已經強調 automated build 與 automated testing。([martinfowler.com](https://www.martinfowler.com/articles/originalContinuousIntegration.html?utm_source=chatgpt.com))

接著出現另一個問題。

Developer 寫的 Unit Test 很精確。

但 Business 說的需求卻可能是：

「使用者登入失敗三次後應被鎖定。」

兩者之間仍然存在翻譯。

BDD 嘗試縮小這個距離。

例如：

```text
Given a user has failed login twice
When the user enters an incorrect password again
Then the account should be locked
```

Given / When / Then 把需求、驗收條件與測試案例放進同一個表達方式。

Dan North 在 2000 年代初發展 BDD，JBehave、RSpec，之後 Cucumber 將這種方式進一步普及。BDD 也逐漸同時成為需求分析方法與 acceptance-level automated testing 的方式。([cucumber.io](https://cucumber.io/docs/bdd/history/?utm_source=chatgpt.com))

這是一個很重要的變化：

**Acceptance Criteria 開始可以直接成為 executable artifact。**

---

## Browser automation 又把驗證推到了 E2E

2004 年，Selenium 在 ThoughtWorks 誕生，最初就是為了自動測試 Web application。([Selenium](https://www.selenium.dev/history/?utm_source=chatgpt.com))

測試邊界因此又向外擴張。

Unit Test 驗證：

```text
function → result
```

Integration Test 驗證：

```text
component A → component B
```

API Test 驗證：

```text
request → service → response
```

而 End-to-End Test 可以驗證：

```text
Browser
→ UI
→ API
→ Application
→ Database
→ response
→ UI
```

今天 Selenium、Cypress、Playwright 等工具讓這種流程變成高度自動化。

Playwright 甚至可以一次跨不同瀏覽器執行、parallel execution、trace、HTML report 等。([playwright.dev](https://playwright.dev/docs/running-tests?utm_source=chatgpt.com))

但這同時造成另一個問題：

E2E 很接近真實使用者，但它通常更慢、更脆弱、環境依賴更多。

所以現代測試並不是：

**E2E 越多越好。**

而是把不同種類的驗證放在不同成本的位置。

於是我們逐漸形成今天熟悉的多層測試：

Unit  
Component  
Integration  
API  
Contract  
System  
E2E  
Acceptance

每一層驗證不同的問題。

---

## Microservices 又增加了一層：Contract Test

當 monolith 逐漸變成 distributed systems 與 microservices，Integration Test 又遇到新的成本問題。

如果 Service A 依賴 B、C、D、E，難道每次驗證 A 都必須把所有 service 啟動？

Contract Testing 因此開始受到重視。

例如 Pact 採用 consumer-driven contract：

Consumer 宣告自己依賴 Provider 的哪些 request / response 行為，再讓 Provider 驗證這份 contract。Pact 最初於 2013 年因 microservices integration testing 的實務問題而產生。([docs.pact.io](https://docs.pact.io/?utm_source=chatgpt.com))

這代表測試不再只有：

「Component 自己是否正確？」

也開始問：

**不同 Component 之間的承諾是否仍然成立？**

---

## 到 DevOps 時代，Test 已經變成 Delivery Gate

當 CI/CD 成熟後，測試的位置再次改變。

以前：

Developer → QA → Release

後來逐漸變成：

Commit  
→ Build  
→ Static Analysis  
→ Unit Test  
→ Integration Test  
→ Contract Test  
→ Security Scan  
→ E2E  
→ Deploy  
→ Smoke Test  
→ Monitoring

JUnit、pytest、Jest 負責不同語言的 unit tests。

Postman / Newman 可以做 API verification。

Pact 可以做 contract testing。

Selenium、Cypress、Playwright 驗證 UI/E2E。

JMeter、k6 驗證 performance。

SAST、DAST、dependency scanners 處理 security。

Jenkins、GitHub Actions、GitLab CI 等把這些驗證組合成 Pipeline。

此時 QA 已經不再是一個「最後負責找 Bug 的部門」。

品質控制逐漸散佈到整個 Software Development Lifecycle。

---

# 然後 AI 出現了

AI 帶來一個非常有意思的問題。

如果 AI 幫我們寫的是普通程式碼，其實原有測試並沒有失效。

AI 產生一個 function，它仍然可以接受 Unit Test。

AI 修改 API，它仍然可以接受 Integration Test、Contract Test。

AI 完成整個 Feature，它仍然可以接受 E2E Test。

所以對 AI-generated software 而言：

**AI 並沒有讓傳統 software testing 消失。**

恰好相反。

當 code generation 的速度變快，人類逐行閱讀所有 generated code 的成本越來越高，automated verification 的重要性反而變大。

SWE-bench 就是一個很典型的例子。

它給 Coding Agent 一個真實 GitHub issue 與 repository，讓 Agent 修改 code，再用 tests 判斷問題是否真的被解決。

其中甚至區分：

FAIL_TO_PASS

原本失敗的 test，修改後應該通過。

以及：

PASS_TO_PASS

原本正常的功能，在修改後仍然必須正常。

因此驗收不只是：

**「AI 有沒有完成需求？」**

還包含：

**「它有沒有破壞原本正常的東西？」** ([OpenAI](https://openai.com/index/introducing-swe-bench-verified/?utm_source=chatgpt.com))

這其實就是 regression testing 的核心思想，只是現在執行程式修改的人可能變成 AI Agent。

---

# 但如果被測試的東西本身就是 AI，問題就不同了

傳統程式通常可以寫：

```text
input = 2 + 2
expected = 4
```

Pass 或 Fail 很明確。

但問 LLM：

```text
請摘要這份 20 頁的合約。
```

什麼叫「正確」？

可能有十種不同寫法，而且全部合理。

再例如 Agent：

```text
Find a flight
compare alternatives
check calendar
book the selected option
send confirmation
```

它可能走不同路徑、呼叫不同工具、產生不同中間狀態。

最後都可能完成任務。

因此 AI Testing 開始碰到傳統 Software Testing 很少如此嚴重面對的問題：

**Test Oracle Problem。**

ISO/IEC TR 29119-11 在討論 AI-based systems testing 時，就特別指出 AI 系統可能具有 poorly specified、non-deterministic 等特性，使 acceptance criteria 與 expected result 更難定義。([ISO](https://www.iso.org/standard/79016.html?utm_source=chatgpt.com))

於是 AI 的測試文件開始變得不同。

除了 Test Case，我們開始需要：

Eval Dataset

Scenario

Expected Properties

Rubric

Grader

Threshold

Failure Taxonomy

Model / Prompt / Configuration Version

Execution Trace

Tool-call Trace

Regression Baseline

Acceptance Report

測試也不一定再是：

```text
expected == actual
```

而可能是：

```text
Task completion ≥ threshold
Factuality ≥ threshold
Safety violation = 0
Tool call correctness ≥ threshold
Regression ≤ tolerance
```

甚至同一個 case 需要執行多次，觀察 success rate 與 variance。

---

# Agent Testing 又把 E2E 往外推了一層

LLM Chatbot 可以測 single response。

Agent 不行。

Agent 可能：

Retrieve data  
Reason  
Call tool  
Modify state  
Observe result  
Make another decision  
Call another tool  
Finally produce an outcome

因此只測 Prompt → Response 已經不足。

Anthropic 在 2026 年討論 agent eval 時也特別指出，Agent 的 multi-turn、tool use、state modification 與 intermediate results，讓傳統 single-turn evaluation 很容易漏掉真正的失敗模式。([Anthropic](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents?utm_source=chatgpt.com))

這非常像二十年前軟體測試遇到的問題重新出現：

Unit Test 不夠，所以出現 Integration Test。

Integration Test 不夠，所以出現 System / E2E Test。

現在：

Prompt Test 不夠。

所以我們又開始建立：

Agent Integration Eval  
Tool-use Eval  
Workflow Eval  
State Eval  
End-to-End Task Eval

測試的邊界再次向外移動。

---

# 更有意思的是：連 Test 本身也開始需要被驗證

2026 年 OpenAI 已公開指出 SWE-bench Verified 因 benchmark contamination 等問題，逐漸不適合繼續衡量 frontier coding capability，並轉而建議新的 benchmark。([OpenAI](https://openai.com/index/why-we-no-longer-evaluate-swe-bench-verified/?utm_source=chatgpt.com))

Google DeepMind 在 2026 年甚至開始實驗 double-blind AI evaluation，用隔離的 evaluation environment 降低模型事先接觸 benchmark 的可能性。([Google DeepMind](https://deepmind.google/blog/piloting-the-worlds-first-double-blind-ai-evaluations/?utm_source=chatgpt.com))

這代表我們進入了一個很有意思的新階段。

以前我們問：

**Software 通過 Test 了嗎？**

現在還必須問：

**這個 Test 本身還有效嗎？**

測試資料有沒有被模型看過？

Judge 是否可靠？

Benchmark 是否代表 Production？

Eval 是否真的測到我們想驗證的能力？

Acceptance threshold 是怎麼決定的？

也就是說：

**AI 不只讓 Software 需要被測試，也讓 Testing System 本身開始成為被驗證的對象。**

---

# 七十年後，我們其實仍然在回答同一個問題

如果把所有工具名稱拿掉：

JUnit  
pytest  
Selenium  
Cucumber  
Pact  
Playwright  
CI/CD  
LLM Eval  
Agent Benchmark

軟體測試七十年的核心問題其實沒有改變。

我們一直在問：

**How do we know this system did what we intended it to do?**

改變的是「System」的範圍。

最開始是一段程式。

後來是一個 module。

再來是一套 application。

接著是一群 distributed services。

再來是一整條 production workflow。

現在則可能是一個能自己閱讀資料、做決策、呼叫工具並改變外部狀態的 AI Agent。

所以測試的演化不只是：

Manual → Automation

也不只是：

Unit → Integration → E2E

更完整的演化其實比較像：

**Acceptance  
→ Test Case  
→ Structured Test Documentation  
→ Automated Unit Test  
→ Executable Specification  
→ Continuous Verification  
→ End-to-End Validation  
→ Runtime Evidence  
→ AI Evaluation**

我們用了七十年的時間，把「我覺得它應該可以運作」逐漸變成：

**Show me the evidence.**

而 AI 時代真正的新問題可能不是：

「AI 能不能寫更多 Test？」

而是：

**當系統的行為開始具有機率性、自主性與多步決策能力時，我們究竟需要什麼證據，才足以說它已經通過驗收？**

這個版本刻意沒有把文章寫成「測試工具史」，而是把工具放在驗收證據的演化裡。它後面其實很自然還能接出另一篇：傳統軟體的 **Unit → Integration → Contract → E2E → Acceptance**，到了 AI Agent 後究竟各自對應成什麼測試層級。

---

**Sources:**

- [Testing References - The History of Software Testing](https://www.testingreferences.com/testinghistory.php?utm_source=chatgpt.com)
- [E.W. Dijkstra Archive: Structured programming (EWD268)](https://www.cs.utexas.edu/~EWD/transcriptions/EWD02xx/EWD268.html?utm_source=chatgpt.com)
- [IEEE SA - IEEE 829-1983](https://standards.ieee.org/ieee/829/1217/?utm_source=chatgpt.com)
- [ISO/IEC/IEEE 29119 series](https://committee.iso.org/sites/jtc1sc7/home/projects/flagship-standards/isoiecieee-29119-series.html?utm_source=chatgpt.com)
- [Continuous Integration](https://martinfowler.com/articles/continuousIntegration.html?utm_source=chatgpt.com)
- [History of BDD | Cucumber](https://cucumber.io/docs/bdd/history/?utm_source=chatgpt.com)
- [History | Selenium](https://www.selenium.dev/history/?utm_source=chatgpt.com)
- [Running and debugging tests | Playwright](https://playwright.dev/docs/running-tests?utm_source=chatgpt.com)
- [Introduction | Pact Docs](https://docs.pact.io/?utm_source=chatgpt.com)
- [Introducing SWE-bench Verified | OpenAI](https://openai.com/index/introducing-swe-bench-verified/?utm_source=chatgpt.com)
- [ISO/IEC TR 29119-11:2020 - Software and systems engineering — Software testing — Part 11: Guidelines on the testing of AI-based systems](https://www.iso.org/standard/79016.html?utm_source=chatgpt.com)
- [Demystifying evals for AI agents \ Anthropic](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents?utm_source=chatgpt.com)
- [Piloting the world's first double-blind AI evaluations — Google DeepMind](https://deepmind.google/blog/piloting-the-worlds-first-double-blind-ai-evaluations/?utm_source=chatgpt.com)

## Prompt:
2026/9/22 下午10:00:26

把這篇縮短到約 1000 英文字，比較適合 X 讀者

## Response:
2026/9/22 下午10:00:31

可以，縮短後應該保留「歷史演化」而不是保留所有細節。X Articles 的讀者通常不需要完整標準史，而需要快速理解：測試為什麼從驗收清單一路變成 Unit、E2E，再走到 AI Eval。

**social_post: **

# From Acceptance Checklists to AI Evals: How Software Testing Evolved

When people talk about software testing today, they often start with Unit Tests.

JUnit. pytest. Jest.

Then Integration Tests, API Tests, and finally Selenium, Cypress, or Playwright for End-to-End testing.

But software testing did not begin with Unit Tests.

Its original question was much simpler:

**Did the system do what we expected it to do?**

That question has remained surprisingly stable for more than 70 years.

What changed was the size of the system, the complexity of its behavior, and the evidence required before we were willing to accept it.

## 1950s–1970s: Testing separates from debugging

In early software development, programming, testing, and debugging were often treated as closely related activities.

A programmer wrote code, ran it, found an error, fixed it, and ran it again.

Gradually, testing became a distinct engineering activity.

The basic structure was already familiar:

**Input → Execution → Expected Result → Actual Result → Acceptance**

The tools were primitive compared with today, but the logic was already there.

As systems became larger, testing also expanded beyond simply finding bugs.

Black-box testing, white-box testing, functional testing, verification, and validation all emerged around a broader question:

**How much confidence do we have that the system behaves as intended?**

This also produced one of software engineering's most persistent lessons:

Passing tests does not prove that software contains no defects.

It only provides evidence that the tested behaviors worked under the tested conditions.

That distinction is still important today, especially in AI.

## 1980s: Testing becomes documented engineering

By the 1980s, testing was no longer just a collection of test cases.

Formal test documentation began to include artifacts such as:

Test Plans, Test Designs, Test Cases, Test Procedures, Test Logs, Incident Reports, and Test Summary Reports.

This changed the role of testing.

A test was not only something that was executed.

It became something that could be reviewed, repeated, audited, and traced.

This is also where the distinction between **testing** and **quality assurance** becomes clearer.

Testing asks:

**Did this behavior produce the expected result?**

QA asks broader questions:

Were the requirements clear?

Were enough scenarios tested?

Were defects tracked?

Were changes retested?

Can we show evidence of what was verified?

Testing became part of a quality system.

## 1990s: Unit Testing moves verification next to the code

The next major shift was moving testing closer to implementation.

xUnit frameworks, JUnit, and similar tools made automated Unit Testing part of everyday development.

Instead of waiting until an entire application was complete, developers could verify individual functions, classes, and modules continuously.

The validation boundary became smaller:

**Function → Expected Result**

This dramatically reduced verification cost.

A developer no longer needed to manually retest an entire application after every small change.

Thousands of local behaviors could be checked automatically.

Then Test-Driven Development pushed testing even earlier.

Instead of:

**Code → Test**

TDD encouraged:

**Test → Code → Refactor**

Tests were no longer only verification artifacts.

They also became a form of **executable specification**.

## 2000s: Requirements start becoming executable

Agile development shortened delivery cycles.

Testing after months of development no longer worked well when software changed every day.

Continuous Integration moved automated tests directly into the delivery workflow.

A code change could trigger:

Build → Unit Test → Integration Test → Report

At the same time, Behavior-Driven Development connected business expectations with executable tests.

A requirement such as:

> A user should be locked after three failed login attempts.

could become:

```text
Given the user has failed login twice
When another incorrect password is entered
Then the account should be locked
```

Acceptance criteria started becoming machine-executable artifacts.

That was an important transition.

Testing was no longer only checking implementation.

It increasingly linked:

**Requirement → Behavior → Test → Evidence**

## 2000s–2010s: Testing expands toward E2E

Browser automation pushed the testing boundary outward again.

Unit Tests verify individual components.

Integration Tests verify components working together.

API Tests verify service behavior.

Contract Tests verify whether systems still honor agreed interfaces.

End-to-End Tests verify complete user journeys.

An E2E flow may look like:

**Browser → UI → API → Service → Database → Response → UI**

Tools such as Selenium, Cypress, and Playwright made this increasingly automated.

But E2E testing also revealed another engineering reality:

The closer a test gets to the real system, the more expensive and fragile it usually becomes.

Modern testing therefore became layered rather than simply "more E2E."

A typical stack might include:

Unit  
Component  
Integration  
API  
Contract  
System  
E2E  
Acceptance

Each layer answers a different question at a different cost.

## DevOps: Testing becomes a delivery gate

With CI/CD, testing moved from being a development activity to becoming part of software delivery infrastructure.

A modern pipeline may look like:

**Commit  
→ Build  
→ Static Analysis  
→ Unit Test  
→ Integration Test  
→ Contract Test  
→ Security Scan  
→ E2E  
→ Deploy  
→ Smoke Test  
→ Monitoring**

Testing is now distributed across the Software Development Lifecycle.

QA is no longer simply a team waiting at the end to find bugs.

Quality evidence is generated continuously.

## Then AI changed the problem again

If AI generates ordinary software, traditional testing still works.

AI-generated functions can still have Unit Tests.

AI-modified APIs can still have Integration and Contract Tests.

AI-generated features can still be tested through E2E flows.

In fact, automated testing may become even more important when code is generated faster than humans can inspect every line.

But testing changes significantly when **the system being tested is itself AI**.

Traditional software often allows us to write:

```text
Input: 2 + 2
Expected: 4
```

An LLM may instead receive:

> Summarize this contract.

There may be many acceptable answers.

An Agent may:

Retrieve information, reason, call tools, modify state, observe results, make another decision, and continue until a task is complete.

Different execution paths may all be acceptable.

The simple model:

**Expected Result == Actual Result**

is no longer enough.

AI testing increasingly requires artifacts such as:

Eval datasets  
Scenarios  
Rubrics  
Graders  
Thresholds  
Failure taxonomies  
Model and prompt versions  
Tool-call traces  
Regression baselines  
Acceptance reports

A result may look more like:

**Task completion ≥ threshold  
Factuality ≥ threshold  
Unsafe behavior = 0  
Tool-call correctness ≥ threshold  
Regression ≤ tolerance**

And sometimes the same scenario must be executed multiple times because the system is probabilistic.

## From E2E to Agent Evals

Agentic systems push the testing boundary outward once again.

Testing a single prompt and response is not enough when the system can take multiple actions.

We may need to test:

Prompt behavior  
Retrieval quality  
Tool selection  
Tool arguments  
Intermediate decisions  
State changes  
Recovery behavior  
Final task completion

This is effectively a new form of End-to-End testing.

The difference is that the execution path itself may not be deterministic.

## Seventy years later, the question is still the same

If we remove the names of all the tools—JUnit, pytest, Selenium, Playwright, Pact, CI/CD, LLM Evals—the core question has barely changed:

**How do we know this system did what we intended it to do?**

What changed is the meaning of "system."

First it was a program.

Then a function.

Then an application.

Then distributed services.

Then an entire production workflow.

Now it may be an AI Agent that interprets information, makes decisions, calls tools, and changes external state.

So the history of software testing is not simply:

**Manual → Automated**

or:

**Unit → Integration → E2E**

It is closer to:

**Acceptance  
→ Test Cases  
→ Structured Test Documentation  
→ Automated Unit Tests  
→ Executable Specifications  
→ Continuous Verification  
→ End-to-End Validation  
→ AI Evaluation**

For decades, software engineering has been turning:

**"I think it works."**

into:

**"Show me the evidence."**

AI does not change that principle.

It changes what evidence we need.

這版大約就是 X Articles 比較容易讀完的長度，而且主線只剩一條：**驗收對象不斷擴大，因此測試證據、文件與工具也跟著演化。**

## Prompt:
2026/9/22 下午10:07:29

![a85ca70c-b783-419b-82f9-750c2669395b.png](https://chatgpt.com/backend-api/estuary/content?id=file_0000000051308207ba3ab9c5563a1814&fn=a85ca70c-b783-419b-82f9-750c2669395b.png&cd=attachment&ts=497260&p=fs&cid=1&sig=48a8a304b00c5d9e6801835ecbdf0b8b4f11fd0d44a8a7d0f14f73806d811004&v=0)

給一個封面圖

## Response:
2026/9/22 下午10:07:33

![從驗收清單到 AI 評估的測試演進](https://chatgpt.com/backend-api/estuary/content?id=file_0000000043b881f5901a49970741dd63&fn=%E5%BE%9E%E9%A9%97%E6%94%B6%E6%B8%85%E5%96%AE%E5%88%B0+AI+%E8%A9%95%E4%BC%B0%E7%9A%84%E6%B8%AC%E8%A9%A6%E6%BC%94%E9%80%B2.png&cd=attachment&ts=497260&p=fs&cid=1&sig=b34a32f4b5702a487c786fd59dbab6247f1966883ad504d36cdc2348164070b8&v=0)

## Prompt:
2026/9/22 下午11:15:23

![a02dc769-d6ae-49c0-9313-04cb994d8e1e.png](https://chatgpt.com/backend-api/estuary/content?id=file_00000000a424820dbd8e90bd4b688e9f&fn=a02dc769-d6ae-49c0-9313-04cb994d8e1e.png&cd=attachment&ts=497260&p=fs&cid=1&sig=0f0a92fab4902328dc7ac26f7a5919e0f4d4b9eda95e40d9f74cd5eabca45ec9&v=0)

caption 使用問句 
當你們在使用 AI Gen Code 時，誰產生測試規格，誰產生測試程式，誰執行測試，測試範圍包含那些

## Response:
2026/9/22 下午11:15:31

可以直接寫成這樣：

**When you use AI-generated code, who writes the test specification, who generates the test code, who runs the tests—and what does your test scope actually cover? Unit, integration, contract, E2E, acceptance… or only what the AI happened to generate?**

如果想更像 X、再尖銳一點：

**When AI generates the code, who owns the tests? Who defines the test spec, who writes the test code, who executes it—and how far does the test scope go: Unit, Integration, E2E, or real acceptance?**

更偏向文章主題的版本：

**AI can generate code. But who defines what “passed” means? Who creates the test specification, writes the tests, runs them, and decides whether Unit, Integration, E2E, and acceptance coverage are enough?**



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)