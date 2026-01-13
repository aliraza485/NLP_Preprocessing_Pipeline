# NLP Preprocessing Pipeline: From Raw Data to Intelligence
**Internship Project | General Artificial Intelligence Research Lab (GAIRL)**

## 📌 Project Overview
This repository contains a robust NLP preprocessing pipeline built to handle unstructured customer support data. As we move from the **Sequential Era** of RNNs to the **Parallel Era** of Transformers, the quality of input data remains the most critical factor for model accuracy.

## 🛠️ Features
- **Normalization:** Standardizing text to lower case to reduce vocabulary noise.
- **Regex Tokenization:** Custom regex patterns to handle punctuation and special characters without losing context.
- **Stop Word Removal:** Filtering high-frequency, low-value words to focus on user intent.
- **Porter Stemming:** Reducing words to their root form (e.g., *delivery* -> *deliveri*) to shrink vocabulary size by 30-50%.

## 📂 Dataset
The pipeline was tested on `customer_support_dataset.csv`, consisting of 200+ raw support queries.

### Results (Before & After)
| Original Text | Processed Output |
| :--- | :--- |
| "I want to return my order" | `want return order` |
| "My charger is not working" | `charger work` |
| "The delivery is very late" | `deliveri late` |

## 🚀 How to Run
1. Clone the repo: `git clone https://github.com/your-username/airl-nlp-task.git`
2. Install dependencies: `pip install pandas nltk`
3. Run the script: `python preprocessing_script.py`

## 🎓 Acknowledgments
Special thanks to my mentors at the **GAIRL Lab, UET Lahore** for their guidance during this internship task.
