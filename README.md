# FUTURE_DS_3
# 🎓 Student Feedback Sentiment & Keyphrase Analysis

## 📌 Project Overview
This project is an end-to-end Natural Language Processing (NLP) solution designed to analyze student feedback on faculty performance. It automates the extraction of insights from raw textual comments by calculating sentiment scores and extracting relevant key phrases.

The processed data is subsequently exported to build an interactive **Power BI Dashboard** for visual storytelling and trend analysis.

## 🚀 Features
* **Sentiment Analysis:** Utilizes a pre-trained BERT model (`nlptown/bert-base-multilingual-uncased-sentiment`) to assign a sentiment score (1-5) to every student comment.
* **Sentiment Labeling:** Categorizes scores into human-readable labels:
    * 1-2: Negative
    * 3: Neutral
    * 4-5: Positive
* **Keyphrase Extraction:** Implements **KeyBERT** to extract the top 3 most relevant n-grams (1-10 words) from each comment to understand the "why" behind the score.
* **Data Transformation:** Cleans and structures raw Excel data into a refined CSV format ready for analytics.
* **Dashboard Integration:** Includes a Power BI (`.pbix`) file for visualizing the sentiment distribution and key topics.

## 🛠️ Tech Stack
* **Language:** Python 3.10
* **Libraries:**
    * `transformers` (Hugging Face)
    * `keybert`
    * `torch` (PyTorch)
    * `pandas` & `numpy`
* **Visualization:** Microsoft Power BI

## 📂 Files Description
* `main.ipynb`: The Jupyter Notebook containing the data extraction, preprocessing, model inference, and export logic.
* `dashboard.pbix`: The Power BI report file connected to the processed data.
* `student_feedback_sentiment.csv`: The final output file containing comments, sentiment scores, and extracted keywords.

## ⚙️ How It Works
1.  **Data Loading:** Reads raw student feedback from an Excel file.
2.  **Model Inference:**
    * Feeds comments into the BERT tokenizer and model.
    * Calculates the `argmax` of the logits to determine the star rating (1-5).
3.  **Keyword Extraction:** Uses KeyBERT embeddings to find phrases that best represent the semantic meaning of the comment.
4.  **Export:** Saves the enriched dataset for the BI layer.

## 📊 Usage
1.  Install dependencies:
    ```bash
    pip install pandas transformers torch keybert
    ```
2.  Run the notebook `main.ipynb`.
3.  Open `dashboard.pbix` and refresh the data source to point to the generated CSV.

## 🤖 Models Used
* **Sentiment:** [nlptown/bert-base-multilingual-uncased-sentiment](https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment)
* **Keywords:** [KeyBERT](https://maartengr.github.io/KeyBERT/)

---
*Created by [Kazim]*
