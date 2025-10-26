# love_Island-_Sentiment_Analysis


This project performs **sentiment analysis** on a large dataset of *Love Island* discussions, containing **over 20,000 text entries**, to understand public emotion and audience perception using advanced **Natural Language Processing (NLP)** and **Machine Learning** techniques.  
It leverages both **rule-based** (VADER) and **statistical** (TF-IDF + ML models) approaches to classify sentiments as **Positive**, **Neutral**, or **Negative**.

The project also features an **interactive Streamlit app** where users can test real-time predictions using **three different models**.

---

## 🧠 Project Overview  

The goal of this project is to capture and analyze how audiences feel about *Love Island* episodes, contestants, and events through text-based sentiment classification.  
The dataset includes 20,000+ rows of audience opinions, cleaned, processed, and analyzed through multiple sentiment models for maximum accuracy and interpretability.  

To ensure optimal model performance, **Naive Bayes was tuned using GridSearchCV** — a crucial step since the baseline Naive Bayes model, while fast and simple, underperformed due to high bias.  
Hyperparameter tuning helped **boost accuracy** and improve prediction balance across all sentiment classes.

---

## ⚙️ Key Features  

✅ Large dataset with **20,000+ rows** for realistic sentiment training  
✅ Dual-layer approach: **VADER** (lexicon-based) + **TF-IDF Machine Learning models**  
✅ Multiple models trained and compared:
- **Baseline Naive Bayes**
- **Hyperparameter-Tuned Logistic Regression**
- **Hyperparameter-Tuned Naive Bayes**
- **Ensemble Voting Classifier**
✅ **TF-IDF** used for feature extraction  
✅ **GridSearchCV** used for hyperparameter tuning  
✅ **Streamlit app** allows live sentiment prediction using any of the three main models  
✅ Detailed visualizations using **Matplotlib** and **WordCloud**  

---

## 🧩 Tech Stack  

| Category | Tools / Libraries Used |
|-----------|------------------------|
| Programming | Python (Pandas, NLTK, Scikit-learn, Matplotlib, WordCloud) |
| Visualization | Streamlit |
| Feature Extraction | TF-IDF (Term Frequency–Inverse Document Frequency) |
| Model Optimization | GridSearchCV |
| Machine Learning Models | Naive Bayes, Logistic Regression, Voting Classifier |
| Data Format | CSV / Excel |
| Environment | Jupyter Notebook, Streamlit App |

---

## 🧾 Project Steps  

1. **Data Collection & Cleaning**  
   - Imported and structured dataset in Excel with 20,000+ text records.  
   - Fixed misaligned columns using *Delimited → Comma* separation.  

2. **Text Preprocessing**  
   - Removal urls, hashtags and numbers , stopword removal,and punctuation cleaning.  
   - Transformed text into numeric features using **TF-IDF Vectorization**.  

3. **Sentiment Labeling with VADER**  
   - Used `SentimentIntensityAnalyzer()` from NLTK to assign polarity scores (compound).  
   - Labeled each sentence as *Positive*, *Neutral*, or *Negative*.  

4. **Model Training & Tuning**  
   - **Baseline Naive Bayes**: Provided a good start but limited performance due to strong assumptions.  
   - **Tuned Naive Bayes**: Hyperparameters (`alpha`, `fit_prior`) optimized via GridSearchCV to boost accuracy.  
   - **Tuned Logistic Regression**: Fine-tuned `C` and `solver` parameters for improved balance.  
   - **Voting Classifier Ensemble**: Combined tuned NB + LR to achieve stable, high-accuracy results.  

5. **Streamlit App Development**  
   - Developed an interactive app with **three selectable models** for real-time predictions.  
   - Includes visual charts, sentiment breakdowns, and word cloud visualizations.  

---

## 📊 Model Performance Results  

### 🔹 Baseline Naive Bayes
Accuracy: 0.6867
Precision / Recall / F1:
Negative: 0.87 / 0.42 / 0.57
Neutral:  0.82 / 0.46 / 0.59
Positive: 0.63 / 0.96 / 0.76

---

### 🔹 Hyperparameter-Tuned Logistic Regression

Best Params: {‘C’: 10, ‘solver’: ‘liblinear’}
Accuracy: 0.8496
Precision / Recall / F1:
Negative: 0.82 / 0.70 / 0.76
Neutral:  0.82 / 0.87 / 0.85
Positive: 0.88 / 0.92 / 0.89

---

### 🔹 Hyperparameter-Tuned Naive Bayes

Best Params: {‘alpha’: 1.0, ‘fit_prior’: False}
Accuracy: 0.7532
Precision / Recall / F1:
Negative: 0.65 / 0.73 / 0.68
Neutral:  0.76 / 0.69 / 0.72
Positive: 0.81 / 0.81 / 0.81

---

### 🔹 Ensemble (Voting Classifier: Tuned NB + LR)  

Accuracy: 0.8459
Precision / Recall / F1:
Negative: 0.81 / 0.71 / 0.76
Neutral:  0.82 / 0.86 / 0.84
Positive: 0.88 / 0.91 / 0.89


The **Voting Classifier Ensemble** achieved the most balanced results, proving effective for large datasets with mixed sentiment tone.

---

## 🌐 Streamlit Dashboard  

The **Streamlit app** allows users to select and test any of the three models:  
1. **Tuned Logistic Regression (`best_lr.pkl`)**  
2. **Tuned Naive Bayes (`best_nb.pkl`)**  
3. **Voting Classifier Ensemble (`ensemble_tuned.pkl`)**  

Each model loads dynamically, predicts sentiment for new input text, and displays:  
- Model Accuracy & Classification Report  
- Sentiment Distribution Chart  
- Word Cloud for Frequent Words  

---

## 📁 Files Included  

| File | Description |
|------|-------------|
| `untitled.ipynb` | Full Jupyter Notebook (data cleaning, training, tuning) |
| `app.py` | Streamlit dashboard for model predictions |
| `love_island_tweets.xlsx` | Final cleaned dataset (20,000+ rows) |
| `best_lr.pkl` | Tuned Logistic Regression model |
| `best_nb.pkl` | Tuned Naive Bayes model |
| `ensemble_tuned.pkl` | Ensemble Voting Classifier (LR + NB) |


---
