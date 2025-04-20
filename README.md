# 📰 Arabic News Semantic Scoring with Sentence Transformers

This project involves scraping Arabic news articles from Al Jazeera, analyzing their semantic similarity to a reference sentence using a multilingual **Sentence Transformer**, and scoring them accordingly. The ultimate goal is to build a dataset for potential fine-tuning of language models or for further NLP research.

---

## 📌 Features

- **Web Scraping**: Automatically scrapes Arabic news articles from Al Jazeera.
- **Text Preprocessing**: Cleans and tokenizes Arabic text.
- **Semantic Scoring**: Uses a multilingual Sentence Transformer to calculate similarity with a reference sentence.
- **Dataset Creation**: Stores the scraped and processed data into a structured CSV file.
- **Future Ready**: Ready for integration into a fine-tuning pipeline using Transformers.

---

## 🛠️ Technologies Used

- Python
- `sentence-transformers`
- `transformers` (HuggingFace)
- `nltk`
- `beautifulsoup4`
- `pandas`
- `scikit-learn`
- PyTorch

---

## 🚀 Installation

First, make sure you have Python ≥ 3.7. Install required packages:

```bash
pip install sentence-transformers transformers beautifulsoup4 nltk datasets accelerate
```

---

## 📂 Project Structure

```
atelier3.ipynb         # Main notebook
arabic_dataset.csv     # Output CSV dataset (after running)
```

---

## 📋 How It Works

### 1. Reference Definition
Defines a reference sentence in Arabic:
```python
reference = "هذا النص يتحدث عن التعليم في الوطن العربي"
```

### 2. Article Scraping
Scrapes recent Arabic news articles from Al Jazeera using BeautifulSoup.

### 3. Preprocessing
- Cleans HTML.
- Retains Arabic-only characters.
- Removes stopwords and short words using NLTK's Arabic stopword list.

### 4. Semantic Similarity
Computes similarity between each article and the reference using:
```python
sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2
```
The result is scaled into a 0–10 score.

### 5. Dataset Creation
Stores the result as:
```csv
Text, Score, tokens
```

---

## 🧪 Sample Output

| Text (truncated)        | Score | Tokens                  |
|-------------------------|-------|--------------------------|
| "في خطوة جديدة..."       | 8.45  | [خطوة, جديدة, ...]       |

---

## 📈 Potential Extensions

- Fine-tune GPT-2 or other LLMs using the generated data.
- Extend scraping to multiple Arabic sources.
- Create datasets for other semantic tasks: classification, summarization, etc.

---

## 📜 License

This project is open-source and available under the MIT License.
