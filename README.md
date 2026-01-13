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


