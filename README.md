# Sentiment Analysis of Political Discourse on Twitter  
### Trump vs. Harris — A Multi-Model Comparison

This project performs a **comparative sentiment analysis** on Twitter data referencing **Donald Trump** and **Kamala Harris**. The objective is to evaluate **how different sentiment analysis approaches behave on political social-media text**, and to identify which methods are most suitable for real-time, noisy, and context-rich data such as tweets.

We compare **deep learning models** with **lexicon-based methods**, analyze sentiment distributions, and study engagement patterns through retweet weighting.

---

## 📌 Project Objectives

- Analyze public sentiment toward Donald Trump and Kamala Harris on Twitter
- Compare multiple sentiment analysis libraries:
  - **RoBERTa**
  - **VADER**
  - **TextBlob**
  - **AFINN**
- Evaluate each method's strengths, limitations, and real-world suitability
- Examine sentiment distributions and engagement patterns
- Identify the most practical sentiment analysis tool for social media data

---

## 🗂️ Data Overview

- **Source:** Twitter (tweets mentioning Trump or Harris)
- **Textual Features:** Tweet text, emojis, hashtags, mentions
- **Engagement Feature:** Retweet count (used as sentiment weight)
- **Target Output:**  
  - Positive  
  - Neutral  
  - Negative  

---

## 🔄 Methodology

### 1. Data Cleaning & Preprocessing
- Removal of:
  - User mentions (`@username`)
  - URLs
  - Hashtags
  - Special characters and punctuation
- Lowercasing for text standardization
- Stopword removal
- Lemmatization
- Emoji conversion to text (e.g., 😡 → *angry face*)
- Duplicate removal
- Handling missing values
- Retweet weighting to amplify high-engagement tweets

---

### 2. Sentiment Models Used

#### 🔹 RoBERTa (Transformer-Based)
- Model: `cardiffnlp/twitter-roberta-base-sentiment`
- Fine-tuned specifically for Twitter data
- Supports **Negative / Neutral / Positive** classification
- Context-aware and robust to linguistic nuance
- Computationally expensive but high accuracy

#### 🔹 VADER (Lexicon-Based)
- Designed specifically for social media text
- Handles:
  - Emojis
  - Capitalization
  - Punctuation
  - Negation
- Produces a **compound sentiment score**
- Extremely fast and lightweight

#### 🔹 TextBlob
- Lexicon-based with rule + statistics
- Easy to use and fast
- Limited context awareness
- Less effective with sarcasm or complex phrasing

#### 🔹 AFINN
- Word-level sentiment scoring
- Simple and interpretable
- No contextual understanding
- Best suited for quick baseline analysis

---

### 3. Sentiment Classification
- Tweets classified into:
  - **Positive**
  - **Negative**
  - **Neutral**
- Each model evaluated independently
- Outputs normalized for comparison

---

### 4. Visualization & Analysis
- Bar charts for sentiment distribution
- Pie charts for proportional sentiment comparison
- Topic-wise sentiment comparisons
- Sentiment vs. retweet engagement analysis

---

## 📊 Key Findings

### Sentiment Distribution
- **Neutral sentiment dominates** for both Trump and Harris
- Trump tweets show **higher negative sentiment** overall
- Positive sentiment is low for both candidates, indicating critical or disengaged political discourse on Twitter

### Engagement Insights
- Trump-related tweets show **wider engagement spread**
- Both positive and negative tweets can go viral
- No strong correlation between sentiment polarity and retweet count

---

## 🏆 Model Comparison Summary

| Feature | RoBERTa | VADER | TextBlob | AFINN |
|---------|---------|-------|----------|-------|
| Context Awareness | ✅ Yes | ❌ No | ❌ No | ❌ No |
| Handles Emojis & Slang | ✅ Yes | ✅ Yes | ❌ No | ❌ No |
| Speed | ❌ Slow | ✅ Very Fast | ✅ Fast | ✅ Fast |
| Accuracy | ✅ Very High | 🟡 Medium-High | 🟡 Medium | 🔴 Low-Medium |
| Best Use Case | Deep analysis | Real-time social media | Simple sentiment | Baseline scoring |

---

## 🥇 Final Conclusion

**VADER** emerged as the most practical tool for this use case due to:
- Real-time performance
- Robust handling of social-media language
- Low computational cost
- High interpretability

**RoBERTa** remains the best choice for:
- Research-grade analysis
- Long-form or complex political text
- Domain-specific fine-tuning

---

## 🛠️ Tech Stack

- **Python**
- **Pandas**
- **NLTK**
- **Scikit-learn**
- **Transformers (Hugging Face)**
- **Matplotlib / Seaborn**

---

## 📁 Repository Structure
```
├── Sentiment Analysis Final.ipynb       # Full implementation
├── Sentiment_Analysis_Presentation.pdf  # Final presentation
└── README.md                            # Project documentation
```

---

## 🚀 How to Run

1. **Clone the repository**
```bash
   git clone <repository-url>
   cd <repository-name>
```

2. **Install dependencies**
```bash
   pip install pandas nltk transformers torch vaderSentiment textblob afinn matplotlib seaborn
```

3. **Download NLTK resources** (first run only)
```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   nltk.download('wordnet')
```

4. **Run the notebook**
```bash
   jupyter notebook "Sentiment Analysis Final.ipynb"
```

---

## 📈 Future Improvements

- Temporal sentiment analysis over election cycles
- Topic-aware sentiment modeling
- Sarcasm detection using transformer fine-tuning
- Network-based analysis of retweet propagation
- Integration with real-time Twitter streaming APIs

---

## 👥 Contributors

- Talha Gulzar
- Rezoon
- Anoushka
- Ria
- Kaanchi

---

## 📧 Contact

**Talha Gulzar**  
MS in Business Analytics  
Babson College
  
🔗 LinkedIn: [linkedin.com/in/talhagulzar2](https://www.linkedin.com/in/talhagulzar2)

---
