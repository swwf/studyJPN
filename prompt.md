# 日語字彙表填寫規則 v2.0

本文檔為日語學習系統的字彙資料建立規則，輸出格式為JSON結構，適用於N5-N1各級別單字管理。

## 輸出格式說明

每個單字需要包含以下欄位，請依照JSON格式輸出：

```json
{
  "id": 1,
  "number": {
    "japanese": "いち",
    "romaji": "ichi"
  },
  "word": {
    "hiragana": "くるま",
    "romaji": "kuruma",
    "kanji": "車",
    "meaning": "汽車",
    "part_of_speech": "名詞",
    "level": "N5"
  },
  "example": {
    "japanese": "車を運転します。",
    "romaji": "kuruma o unten shimasu.",
    "chinese": "駕駛汽車。"
  },
  "memory_aid": "相關詞：電車 (densha - 火車/電車)、自転車 (jitensha - 腳踏車)",
  "advanced_phrase": {
    "japanese": "車が大好きです。",
    "romaji": "kuruma ga daisuki desu.",
    "chinese": "我很喜歡車子。"
  }
}
```

## 各欄位填寫規則

### 1. `id` (編號)

- **規則：** 按照單字新增順序填寫連續的阿拉伯數字
- **範例：** 1, 2, 3, 4...

### 2. `number` (數字讀音)

- **japanese：** 該編號的日文讀音（平假名）
- **romaji：** 該編號的羅馬字讀音
- **範例：** 1號 → {"japanese": "いち", "romaji": "ichi"}

### 3. `word` (單字資訊)

- **hiragana：** 單字的平假名寫法
- **romaji：** 單字的羅馬字寫法
- **kanji：** 單字的漢字寫法（若無漢字則留空字串 ""）
- **meaning：** 單字的中文意思
- **part_of_speech：** 詞性（名詞、動詞、形容詞、副詞等）
- **level：** 該單字的JLPT級別（N5、N4、N3、N2、N1）

### 4. `example` (例句)

- **japanese：** 日文例句
- **romaji：** 例句的羅馬字
- **chinese：** 例句的中文翻譯

### 5. `memory_aid` (記憶輔助)

- **規則：** 提供記憶技巧、相關單字、語法提示等
- **範例：** "相關詞：電車 (densha - 火車/電車)、自転車 (jitensha - 腳踏車)"

### 6. `advanced_phrase` (進階短句)

- **japanese：** 更進階的日文短句
- **romaji：** 進階短句的羅馬字
- **chinese：** 進階短句的中文翻譯

## 詞性分類標準

### 主要詞性類別：

- **名詞** - 人、事、物的名稱
- **動詞** - 表示動作或狀態的詞
- **形容詞** - 描述性質、狀態的詞（包含い形容詞和な形容詞）
- **副詞** - 修飾動詞、形容詞的詞

### 顏色標示系統：

- **名詞** → 綠色標示 (#28a745)
- **動詞** → 藍色標示 (#007bff)
- **形容詞** → 黃色標示 (#ffc107)
- **副詞** → 紫色標示 (#6f42c1)
- **其他** → 灰色標示 (#6c757d)

## 級別標準

### JLPT級別對應：

- **N5** - 最基礎單字，日常生活常用
- **N4** - 基礎單字，簡單會話
- **N3** - 中級單字，一般交流
- **N2** - 中高級單字，商務場合
- **N1** - 高級單字，學術專業

## 完整JSON檔案結構

```json
{
  "metadata": {
    "title": "日語N5單字學習資料",
    "description": "包含XX個N5級別的日語單字，附有平假名、漢字、羅馬字、中文翻譯、例句及記憶輔助",
    "level": "N5",
    "total_words": 42,
    "created_date": "2024"
  },
  "words": [
    // 單字陣列，每個元素都是上述的單字物件
  ]
}
```

## 品質控制要求

1. **一致性：** 所有單字的格式必須完全一致
2. **正確性：** 平假名、羅馬字、漢字必須正確無誤
3. **實用性：** 例句要貼近日常使用情境
4. **教學性：** 記憶輔助要有實際幫助
5. **完整性：** 所有欄位都必須填寫，不可遺漏

## 範例格式預覽

```json
{
  "metadata": {
    "title": "日語N5單字學習資料",
    "description": "包含5個N5級別的日語單字範例",
    "level": "N5",
    "total_words": 5,
    "created_date": "2024"
  },
  "words": [
    {
      "id": 1,
      "number": {"japanese": "いち", "romaji": "ichi"},
      "word": {
        "hiragana": "くるま",
        "romaji": "kuruma",
        "kanji": "車",
        "meaning": "汽車",
        "part_of_speech": "名詞",
        "level": "N5"
      },
      "example": {
        "japanese": "車を運転します。",
        "romaji": "kuruma o unten shimasu.",
        "chinese": "駕駛汽車。"
      },
      "memory_aid": "相關詞：電車 (densha - 火車/電車)、自転車 (jitensha - 腳踏車)",
      "advanced_phrase": {
        "japanese": "車が大好きです。",
        "romaji": "kuruma ga daisuki desu.",
        "chinese": "我很喜歡車子。"
      }
    }
  ]
}
```

---

**注意事項：**

- 請確保JSON格式正確，避免語法錯誤
- 中文翻譯使用台灣慣用詞彙
- 羅馬字採用標準拼寫法
- 例句難度要符合該級別學習者程度

## 使用此規則的指令

當需要新增單字時，請按照以上格式輸出完整的JSON物件，並確保：

- 編號連續
- 資料完整
- 格式正確
- 內容品質符合要求

---

**版本：** v2.0
**更新日期：** 2025-06-22
**適用範圍：** N5-N1日語學習系統
