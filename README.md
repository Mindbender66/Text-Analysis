# 📝 Text Analysis — NLP-Based Article Sentiment & Readability Analyzer

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-NLTK%20%7C%20TextBlob-green)
![BeautifulSoup](https://img.shields.io/badge/Web%20Scraping-BeautifulSoup4-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

A Python-based NLP pipeline that **scrapes articles from URLs**, extracts full text, and computes **15 linguistic & sentiment metrics** — including Fog Index, Polarity, Subjectivity, Syllable counts, and more. Results are exported to a clean Excel report.

---

## 📌 Project Overview

This project was built to automate the analysis of online articles at scale. Given a list of article URLs, the pipeline:

1. Scrapes and extracts article text using **BeautifulSoup**
2. Computes **sentiment scores** (positive, negative, polarity, subjectivity) using **TextBlob**
3. Measures **readability metrics** (Fog Index, avg sentence length, complex word %)
4. Counts **syllables, personal pronouns, word lengths**
5. Saves all results into a structured **Excel output file**

---

## 📁 Project Structure

```
text-analysis/
│
├── text_analysis.py        # Main Python script
├── Input.xlsx              # Input file with URL_ID and URL columns
├── Output.xlsx             # Generated output with all computed metrics
├── Explanation.docx        # Detailed explanation of each metric
├── Extracted_Articles/     # Auto-created folder with saved article .txt files
└── README.md
```

---

## 📊 Output Metrics (15 Features)

| Metric | Description |
|---|---|
| `POSITIVE SCORE` | Count of sentences with positive polarity |
| `NEGATIVE SCORE` | Count of sentences with negative polarity |
| `POLARITY SCORE` | Overall sentiment: -1 (negative) to +1 (positive) |
| `SUBJECTIVITY SCORE` | 0 (objective) to 1 (subjective) |
| `AVG SENTENCE LENGTH` | Average number of words per sentence |
| `PERCENTAGE OF COMPLEX WORDS` | % of words with more than 6 characters |
| `FOG INDEX` | Readability score — higher = harder to read |
| `AVG NUMBER OF WORDS PER SENTENCE` | Similar to avg sentence length |
| `COMPLEX WORD COUNT` | Total count of complex words |
| `WORD COUNT` | Total words in the article |
| `SYLLABLE PER WORD` | Average syllables per word (via CMU Pronouncing Dict) |
| `PERSONAL PRONOUNS` | Count of I, we, me, our, us, etc. |
| `AVG WORD LENGTH` | Average character length per word |

---

## 🧪 Sample Output

| URL_ID | TITLE | POS | NEG | POLARITY | SUBJECTIVITY | FOG INDEX | WORD COUNT |
|---|---|---|---|---|---|---|---|
| blackassign0001 | Rising IT cities... | 21 | 1 | 0.197 | 0.521 | 16.75 | 629 |
| blackassign0002 | Rising IT Cities... | 50 | 13 | 0.119 | 0.427 | 20.29 | 1866 |

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/text-analysis.git
cd text-analysis
```

### 2. Install Dependencies
```bash
pip install pandas requests beautifulsoup4 nltk textblob openpyxl
```

### 3. Download NLTK Resources
These are auto-downloaded when you run the script, but you can also run manually:
```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')
nltk.download('cmudict')
```

### 4. Prepare Input File
Your `Input.xlsx` should have exactly two columns:

| URL_ID | URL |
|---|---|
| blackassign0001 | https://example.com/article1 |
| blackassign0002 | https://example.com/article2 |

### 5. Run the Script
```bash
python text_analysis.py
```

Output will be saved as `Output.xlsx` in the same directory.

---

## 🚀 Run on Google Colab

You can also run this directly in your browser — no setup needed:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1vVBZNX3JOwWYN7b_2pJdaEel4-sZemlw)

> **Note:** Upload your `Input.xlsx` to the Colab session before running.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| `Python 3.8+` | Core language |
| `BeautifulSoup4` | Web scraping & HTML parsing |
| `NLTK` | Tokenization, syllable counting via CMU dict |
| `TextBlob` | Sentiment & subjectivity analysis |
| `Pandas` | Data manipulation & Excel I/O |
| `Requests` | HTTP requests to fetch article pages |
| `openpyxl` | Excel file writing |

---

## 📌 Notes & Limitations

- Some URLs may fail to scrape if they have bot protection or dynamic (JavaScript-rendered) content
- The `syllable_per_word` function relies on the CMU Pronouncing Dictionary — words not in the dictionary are skipped
- `PERCENTAGE OF COMPLEX WORDS` uses a simple heuristic (word length > 6 chars) rather than syllable-based complexity

---

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
