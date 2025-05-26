# Amazon-Feature-Prioritization-

# 🧠 Feature Prioritization Tool Using NLP | Amazon Product Reviews

This project uses Natural Language Processing (NLP) to identify and rank product features from Amazon review data based on **frequency** and **sentiment**. It is designed to help product managers and analysts prioritize feature development and understand customer pain points at scale.

---

## 🔍 Problem Statement

Product teams often struggle with:
- Prioritizing which features to build or improve.
- Understanding what users talk about most—and how they feel about it.

This tool solves that by analyzing **real Amazon customer reviews**, extracting key **nouns (features)**, and ranking them based on how frequently they’re mentioned and how positively or negatively they're received.

---

## 📦 Dataset

Amazon Reviews Polarity dataset from [Kaggle]([https://www.kaggle.com/datasets/bittlingmayer/amazonreviews?resource=download])
- `train.ft.txt.bz2` — 3 million training examples
- `test.ft.txt.bz2` — 650k testing examples  
- Format: `__label__1` or `__label__2` followed by review text

In this project, we used a **subset of 10,000 training and 5,000 testing examples**.

---

## 🛠️ Tools & Technologies

- **Python**
- **TextBlob** (sentiment analysis)
- **SpaCy** (noun extraction & NLP preprocessing)
- **Matplotlib** (visualizations)
- **Pandas / BZ2** (data handling)

---

## ⚙️ How It Works

### 1. **Train Phase**
- Load and clean Amazon review data.
- Extract most common **nouns** from the training set.
- Score features: `frequency × average sentiment`.

### 2. **Test Phase**
- Use extracted features on the test set.
- Check how they're discussed in new reviews.
- Score & rank again based on fresh feedback.

---

## 📈 Output

Top-ranked features from the test data:

| Feature | Frequency | Sentiment | Priority Score |
|---------|-----------|-----------|----------------|
| `book`  | 1653      | 0.158     | 260.72         |
| `time`  | 1124      | 0.151     | 170.17         |
| `story` | 661       | 0.177     | 116.72         |
| `music` | 354       | 0.236     | 83.38          |
| `product` | 379     | 0.140     | 52.92          |

📤 CSV Export: `amazon_feature_priority_test_scored.csv`  
📊 Visualization: Bar chart of features by priority score.

---

## ✅ Business Value

- Helps product managers and analysts **quantify qualitative feedback**
- Reveals **which features users care about** and how they feel
- Can be adapted to **Jira tickets, app reviews, or surveys**

---

## 🚀 Future Improvements

- Streamlit dashboard for interactive prioritization
- Multi-language support (using `langdetect` + translation APIs)
- Topic modeling (LDA) or clustering by feature group
- Support tickets or app store reviews integration

---

## 👤 Author

**Nithin Adru**  
📧 [nithin.adru@email.ucr.edu](mailto:nithin.adru@email.ucr.edu)  
🔗 [LinkedIn](https://www.linkedin.com/in/nithin-adru)

---

## 📜 License

MIT License
