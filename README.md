# social_articles

本專案用來備份與整理各社群平台的貼文與文章草稿，包含單篇內容與系列文章，並以一致的目錄與檔名規則保存不同平台的版本。

## 專案結構

專案包含兩種草稿結構：

1. 單篇 Post / Article：直接依社群平台分類。
2. 系列文章：先依系列主題分類，再依社群平台分類。

```text
social_articles/
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

命名說明：

- `{L|X|M}`：使用平台名稱的識別碼。
  - `L` = Linkedin
  - `X` = X
  - `M` = Medium
- `{SerialAbbreviation}`：使用第一層系列主題目錄中的縮寫。
- `{P|A}`：內容類型，`P` 代表 Post，`A` 代表 Article。
- `{SerialNumber}`：使用兩位數流水號，從 `01` 開始。
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

## 維護原則

- 每個系列主題都應有清楚且唯一的縮寫。
- 同一系列內的文章序號應連續遞增。
- 不同平台的同一篇文章可使用相同序號，方便比對內容版本。
- 單篇與系列草稿的 topic 建議保持在 30 字以內，確保檔名簡潔且容易辨識。
- 檔名欄位統一使用底線 `_` 分隔，只有 topic 內的單字使用連字號 `-` 分隔。
- 草稿內容以 Markdown 撰寫，便於版本控管與跨平台調整。
