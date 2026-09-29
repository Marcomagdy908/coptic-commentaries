# 📖 Coptic Commentaries & Bible Data

**JSON · Arabic Text · Book & Chapter Indexes**

A structured content repository containing Arabic biblical commentary and Bible datasets for reading applications.

## ✨ Contents

- Old Testament commentary in `01_Old_Testament/`.
- New Testament commentary in `02_New_Testament/`.
- Chapter-level commentary and book indexes in `by_book/`.
- Bible divisions and translation-specific book data in `bible/`.

## 🗂️ Data map

| Path | Purpose |
| --- | --- |
| `01_Old_Testament/`, `02_New_Testament/` | Book-level commentary files |
| `by_book/<testament>/<book>/index.json` | Book metadata, contents, and references |
| `by_book/<testament>/<book>/chapter_<n>.json` | Individual commentary chapters |
| `bible/index.json` | Index of grouped Bible divisions |
| `bible/common/`, `bible/jesuit/`, `bible/nkjv/` | Translation-specific book datasets |

Use the indexes to discover available files rather than assuming every translation has identical book identifiers or chapter coverage.

## 🚀 Use the data

No application server or package installation is required. Clone the repository and read the JSON with UTF-8 decoding:

```bash
git clone https://github.com/Marcomagdy908/coptic-commentaries.git
cd coptic-commentaries
```

```python
import json
from pathlib import Path

path = Path("by_book/01_Old_Testament/amos/chapter_7.json")
chapter = json.loads(path.read_text(encoding="utf-8"))
print(chapter["book_title"])
print(chapter["chapter_number"])
for section in chapter["sections"]:
    print(section["text"])
```

## 📋 Example chapter fields

| Field | Meaning |
| --- | --- |
| `book_id`, `book_title` | Book identity |
| `chapter_number`, `chapter_title` | Chapter identity |
| `topic`, `chapter_outline` | Chapter headings |
| `sections_count`, `sections` | Commentary sections |
| `sections[].text` | Section text |
| `sections[].father_name` | Attribution when populated |

Field availability and text completeness vary by file. Preserve source references and attribution when integrating the content; this README does not establish redistribution rights for third-party texts.


---

[Marco Magdy](https://github.com/Marcomagdy908) · [More projects](https://github.com/Marcomagdy908?tab=repositories)
