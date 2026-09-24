# social_articles

本專案用來備份與整理各社群平台的貼文與文章草稿，包含單篇內容與系列文章，並以一致的目錄與檔名規則保存不同平台的版本。

## 專案結構

專案包含兩種草稿結構：

1. 單篇 Post / Article：直接依社群平台分類。
2. 系列文章：先依系列主題分類，再依社群平台分類。

```text
social_articles/
├── raw/                         # 僅存在於工作分支
│   ├── chat.md
│   └── reference.md
├── Linkedin/
│   ├── 20260923_P_trace-id-intro.md
│   └── 20260923_A_backend-roadmap.md
├── X/
│   └── 20260923_P_trace-id-intro.md
├── Medium/
│   └── 20260923_A_backend-roadmap.md
├── TI_TraceID/
│   ├── Linkedin/
│   │   └── L_TI_P_01_trace-id-intro.md
│   ├── X/
│   │   └── X_TI_P_01_trace-id-intro.md
│   └── Medium/
│       └── M_TI_A_01_trace-id-intro.md
└── BRA_BackendRoadmap/
    ├── Linkedin/
    │   └── L_BRA_P_01_backend-learning-path.md
    ├── X/
    │   └── X_BRA_P_01_backend-learning-path.md
    └── Medium/
        └── M_BRA_A_01_backend-learning-path.md
```

`raw/` 為工作分支專用目錄，不納入 `main`；因此 `main` 的實際目錄中不會包含此目錄。

## 原始材料目錄

`raw/` 專門存放撰寫草稿時使用的原始材料，例如：

- Chat 對話內容
- 參考資料與摘錄
- 尚未整理的筆記
- 草稿產生過程中的暫存內容

此目錄僅供撰寫期間使用，可隨時刪除。若內容需要保留，應留在對應的工作分支，不可整合進 `main`。

請勿在 `raw/` 中存放密碼、API Key、Token、個人資料或其他不應進入 Git 歷史的敏感資訊。

## 單篇草稿

不屬於系列的單篇 Post / Article，放在專案根目錄下對應的社群平台目錄：

```text
Linkedin/
X/
Medium/
```

檔案命名格式如下：

```text
{YYYYMMDD}_{P|A}_{topic}.md
```

範例：

```text
20260923_P_trace-id-intro.md
20260923_A_backend-roadmap.md
```

命名說明：

- `{YYYYMMDD}`：預計發布或建立草稿的日期，例如 `20260923`。
- `{P|A}`：內容類型，`P` 代表 Post，`A` 代表 Article。
- `{topic}`：簡短描述內容主題，建議保持在 30 字以內；主題中的單字以連字號 `-` 分隔。
- 各命名欄位之間使用底線 `_` 分隔。
- 檔案副檔名統一使用 `.md`。

## 系列主題目錄命名

系列文章的第一層目錄代表系列主題，命名格式如下：

```text
{縮寫}_{全名}
```

範例：

```text
TI_TraceID
BRA_BackendRoadmap
```

命名原則：

- `{縮寫}` 使用大寫英文字母，作為該系列文章的短代碼。
- `{全名}` 使用可讀性高的英文名稱，可使用 PascalCase 或清楚的英文單字組合。
- 縮寫與全名之間使用底線 `_` 分隔。

## 系列文章的社群網站目錄

系列主題下的第二層目錄代表草稿要發布的社群網站。目前包含：

```text
Linkedin/
X/
Medium/
```

如果未來新增其他平台，請在系列主題目錄底下建立新的平台目錄，並沿用相同的文章檔名規則。

## 系列文章檔案命名

第三層檔案為實際文章草稿，命名格式如下：

```text
{L|X|M}_{SerialAbbreviation}_{P|A}_{SerialNumber}_{topic}.md
```

範例：

```text
L_TI_P_01_trace-id-intro.md
X_TI_P_01_trace-id-intro.md
M_TI_A_01_trace-id-intro.md
L_BRA_P_01_backend-learning-path.md
```

如果 Post 是由某一篇 Article 延伸，為了能從檔名直接辨識對應關係，使用以下格式：

```text
{L|X|M}_{SerialAbbreviation}_P_{ArticleNumber}_{PostNumber}_{topic}.md
```

範例：

```text
L_EIF_A_01_company-ai-adoption.md
L_EIF_P_01_01_company-ai-adoption.md
L_EIF_P_01_02_software-engineering-pipeline.md
L_EIF_A_02_customer-service-ai-adoption.md
L_EIF_P_02_01_customer-service-integration.md
```

在延伸 Post 的檔名中，`P` 後第一組兩位數是對應的 Article 序號，第二組兩位數是該 Article 底下的 Post 序號。例如 `L_EIF_P_02_01` 代表對應 `L_EIF_A_02` 的第 1 篇 Post。

命名說明：

- `{L|X|M}`：使用平台名稱的識別碼。
  - `L` = Linkedin
  - `X` = X
  - `M` = Medium
- `{SerialAbbreviation}`：使用第一層系列主題目錄中的縮寫。
- `{P|A}`：內容類型，`P` 代表 Post，`A` 代表 Article。
- `{SerialNumber}`：使用兩位數流水號，從 `01` 開始。
- `{ArticleNumber}`：延伸 Post 所對應的 Article 兩位數序號。
- `{PostNumber}`：同一篇 Article 底下的 Post 兩位數序號，從 `01` 開始。
- `{topic}`：簡短描述內容主題，建議保持在 30 字以內；主題中的單字以連字號 `-` 分隔。
- 各命名欄位之間使用底線 `_` 分隔。
- 檔案副檔名統一使用 `.md`。

## 新增單篇草稿流程

1. 選擇專案根目錄下對應的社群平台目錄，例如 `Linkedin`。
2. 決定內容類型為 Post（`P`）或 Article（`A`）。
3. 依照日期、類型與主題建立 Markdown 草稿，例如 `20260923_P_trace-id-intro.md`。
4. 同一篇內容若需要不同平台版本，請分別放在對應的平台目錄中。

## 新增系列草稿流程

1. 建立系列主題目錄，例如 `TI_TraceID`。
2. 在系列主題目錄底下建立社群網站目錄，例如 `Linkedin`、`X`、`Medium`。
3. 依照平台、系列縮寫、內容類型、序號與主題建立 Markdown 草稿，例如 `L_TI_P_01_trace-id-intro.md`。
4. 同一篇文章若需要在不同平台保留不同版本，請分別放在對應平台目錄中。

## Git 工作流程

每篇草稿或每組相關草稿應在獨立的工作分支完成，並遵循以下流程：

1. 從最新的 `main` 建立工作分支。
2. 在工作分支建立 `raw/`，放入原始材料或 Chat 內容。
3. 將 `raw/` 內容獨立提交，不可與正式草稿放在同一個 commit。
4. 依照單篇或系列文章的目錄與命名規則撰寫草稿。
5. 將正式草稿獨立提交，且該 commit 不可包含 `raw/` 的變更。
6. 完成後，只將正式草稿的 commit 整合進 `main`。
7. 保留工作分支，讓 `raw/` 只存在於該分支；若不再需要原始材料，也可直接刪除該分支。

為避免 `raw/` 進入 `main` 的 Git 歷史，不可直接 merge 整個工作分支。請從 `main` 使用 `cherry-pick`，只選取不含 `raw/` 的正式草稿 commit：

```shell
git switch main
git cherry-pick <draft-commit>
```

整合前可使用下列指令確認該 commit 不包含 `raw/`：

```shell
git show --stat <draft-commit>
```

## 維護原則

- 每個系列主題都應有清楚且唯一的縮寫。
- 同一系列內的文章序號應連續遞增。
- 不同平台的同一篇文章可使用相同序號，方便比對內容版本。
- 單篇與系列草稿的 topic 建議保持在 30 字以內，確保檔名簡潔且容易辨識。
- 檔名欄位統一使用底線 `_` 分隔，只有 topic 內的單字使用連字號 `-` 分隔。
- 草稿內容以 Markdown 撰寫，便於版本控管與跨平台調整。
- `raw/` 只存在於工作分支，不可出現在 `main` 的檔案或 Git 歷史中。
- `raw/` 與正式草稿必須分開提交，方便只整合正式草稿。
