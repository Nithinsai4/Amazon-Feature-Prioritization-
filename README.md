# 🧠 Amazon Feature Prioritization Tool Using NLP

This project uses **Natural Language Processing (NLP)** to identify and rank product features from Amazon reviews based on their **frequency** and **sentiment**. It helps product managers and analysts **prioritize features**, identify **customer pain points**, and convert qualitative feedback into data-driven insights.

---

## 🔍 Problem Statement

Product teams often struggle to:
- Prioritize which features to improve or build next.
- Understand what customers mention most frequently—and how they feel about it.

This tool automates the process by analyzing Amazon reviews, extracting key **nouns (product features)**, and ranking them based on:
- How often they're mentioned
- How positively (or negatively) they're received

---

## 📦 Dataset

**Source**: [Amazon Reviews Polarity Dataset](https://www.kaggle.com/datasets/bittlingmayer/amazonreviews)  
- `train.ft.txt.bz2`: ~3 million training examples  
- `test.ft.txt.bz2`: ~650k testing examples  
- Format: `__label__1` (negative) or `__label__2` (positive), followed by the review text

**Subset used**:
- 10,000 reviews from the training set
- 5,000 reviews from the test set

---

## 🛠️ Tools & Technologies

- `Python` (core language)
- `SpaCy` (NLP & noun extraction)
- `TextBlob` (sentiment analysis)
- `Pandas`, `BZ2` (data wrangling)
- `Matplotlib` (visualizations)

---

## ⚙️ How It Works

1. **Data Loading**  
   Extract reviews from compressed `.bz2` files, clean them, and assign sentiment labels.

2. **Noun Feature Extraction**  
   Use SpaCy to extract key nouns from each review (lemmatized, lowercased, and filtered).

3. **Sentiment Scoring**  
   Analyze review sentiment using TextBlob, and assign a polarity score (−1 to +1).

4. **Feature Scoring & Ranking**  
   For each frequent noun:
   - Count how often it appears
   - Calculate its average sentiment
   - Compute a **Priority Score = Frequency × Avg. Sentiment**

5. **Visualization**  
   Generate a bar chart ranking features by normalized priority score.

---

## 📈 Sample Output

| Feature   | Frequency | Avg Sentiment | Priority Score |
|-----------|-----------|----------------|----------------|
| book      | 1653      | 0.158          | 260.72         |
| time      | 1124      | 0.151          | 170.17         |
| story     | 661       | 0.177          | 116.72         |
| music     | 354       | 0.236          | 83.38          |
| product   | 379       | 0.140          | 52.92          |

📊 **Bar Chart**: Visualizes top features based on sentiment-weighted importance.

📤 **CSV Output**: `amazon_feature_priority_test_scored.csv`

---

## ✅ Business Value

- Turns messy review data into structured, decision-ready insights
- Helps product teams prioritize based on real customer voice
- Adaptable for other use cases: app reviews, support tickets, surveys, etc.

---

## 🚀 Future Work (Optional Ideas)

- Build a **Streamlit dashboard** for interactive exploration  
- Add **multi-language support** using `langdetect` + translation APIs  
- Use **LDA topic modeling** to group related features  
- Apply this pipeline to **mobile app reviews** or **support tickets**

---

## 👤 Author

**Nithin Adru**  
📧 nithin.adru@email.ucr.edu  

