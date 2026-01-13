# NLP Preprocessing Pipeline: From Raw Data to Intelligence
**Internship Project | General Artificial Intelligence Research Lab (GAIRL)**

## 📌 Project Overview
This repository contains a robust NLP preprocessing pipeline built to handle unstructured customer support data. As we move from the **Sequential Era** of RNNs to the **Parallel Era** of Transformers, the quality of input data remains the most critical factor for model accuracy. This project demonstrates two approaches: traditional rule-based Stemming (NLTK) and modern linguistic Lemmatization (spaCy).



## 🛠️ Features
- **Normalization:** Standardizing text to lower case to reduce vocabulary noise.
- **Regex Tokenization:** Custom regex patterns to handle punctuation and special characters.
- **Stop Word Removal:** Filtering high-frequency, low-value words to focus on user intent.
- **Porter Stemming (NLTK):** Fast root extraction (e.g., *delivery* -> *deliveri*).
- **Lemmatization (spaCy):** Context-aware dictionary base-form extraction (e.g., *better* -> *good*).

## 🔍 Technical Comparison: NLTK vs. spaCy
During the development, I compared **Stemming** (Sequential Era logic) with **Lemmatization** (Parallel Era logic). 

| Feature | NLTK (Stemming) | spaCy (Lemmatization) |
| :--- | :--- | :--- |
| **Method** | Heuristic rules (chopping) | Morphological analysis (dictionary) |
| **Accuracy** | Lower (creates non-words) | Higher (creates valid dictionary words) |
| **Context** | Ignores Part-of-Speech | Uses POS Tagging for accuracy |
| **Example** | `delivery` -> `deliveri` | `delivery` -> `delivery` |



### Results on `customer_support_dataset.csv`
| Original Text | NLTK Result (Stemmed) | spaCy Result (Lemmatized) |
| :--- | :--- | :--- |
| "I want to return my order" | `want return order` | `want return order` |
| "The delivery is very late" | `deliveri late` | `delivery late` |
| "My headphones stopped" | `headphon stop` | `headphone stop` |

## 💻 Implementation (spaCy)
The spaCy pipeline provides a more "intelligent" output by utilizing the `en_core_web_sm` model to understand the linguistic structure of the customer queries.

```python
import spacy
nlp = spacy.load("en_core_web_sm")

def spacy_pipeline(text):
    doc = nlp(text.lower())
    # Filters stop words, punctuation, and returns the dictionary lemma
    return " ".join([token.lemma_ for token in doc if not token.is_stop and not token.is_punct])
