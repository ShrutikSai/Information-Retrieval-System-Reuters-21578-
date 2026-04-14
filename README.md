# 🔍 Information Retrieval & Ranking Optimization System  
**Hybrid Search + Learning-to-Rank on Reuters-21578**

---

## 📌 Overview

This project implements a **production-style Information Retrieval (IR) system** that combines:

- Lexical Search (BM25, TF-IDF)
- Semantic Search (Sentence-BERT)
- Hybrid Ranking (Fusion of lexical + semantic signals)
- Cross-Encoder Re-ranking (for precision improvement)
- Learning-to-Rank (XGBoostRanker / LambdaMART)

The system is evaluated using **industry-standard IR metrics** and demonstrates **significant ranking improvements (~22%)**.

---

## 🎯 Objective

Build a **robust and scalable search system** that:
- Retrieves relevant documents efficiently  
- Improves ranking quality using ML  
- Combines traditional IR + modern NLP techniques  
- Provides measurable performance gains  

---

## 📊 Dataset

- **Source:** Reuters-21578 (NLTK)  
- **Documents:** ~10,000  
- **Queries:**
  - Topic-based queries  
  - Financial keyword queries  
  - Natural-language queries  

---

## 🧠 System Architecture

### 1️⃣ Lexical Retrieval
- **BM25 (Okapi)**  
- **TF-IDF + Cosine Similarity**

✔ Fast and interpretable  
❌ Cannot capture semantic meaning  

---

### 2️⃣ Semantic Retrieval
- **Sentence-BERT (all-MiniLM-L6-v2)**  

✔ Captures contextual meaning  
✔ Handles synonyms  
❌ Computationally expensive  

---

### 3️⃣ Hybrid Retrieval

Combines:
- BM25 scores  
- SBERT similarity  

**Fusion Strategy:**
- Score normalization  
- Weighted combination (0.5 BM25 + 0.5 SBERT)  

---

### 4️⃣ Cross-Encoder Re-Ranking

- Model: `cross-encoder/ms-marco-MiniLM-L-6-v2`

✔ Higher accuracy  
✔ Used for top-K results only  

---

### 5️⃣ Learning-to-Rank (LTR)

- **Model:** XGBoostRanker  

**Features:**
- BM25 score  
- TF-IDF similarity  
- SBERT similarity  
- Document length  
- Term overlap  
- Query length  

✔ Learns optimal ranking from multiple signals  

---

## ⚙️ Pipeline Flow

Query → BM25 Retrieval → Feature Extraction → Hybrid Scoring → Cross-Encoder → LTR → Final Ranking

---

## 📈 Evaluation Metrics

- **Precision@K**
- **nDCG@K**
- **MAP (Mean Average Precision)**

---

## 📊 Results

| System | Performance |
|--------|------------|
| BM25   | Baseline   |
| SBERT  | Improved semantic retrieval |
| Hybrid | Best overall performance |

🚀 Achieved **~22% improvement in ranking quality**

---

## 📉 Advanced Analysis

- Precision@K and nDCG@K curves  
- Per-query comparison  
- Failure analysis  
- Statistical testing:
  - Wilcoxon test  
  - Paired t-test  
- Bootstrap confidence intervals  

---

## 🛠️ Tech Stack

- **Python**
- **SentenceTransformers**
- **Transformers (HuggingFace)**
- **XGBoost**
- **Scikit-learn**
- **rank_bm25**
- **Pandas, NumPy**
- **Matplotlib, Seaborn**

---

## 📂 Project Structure

├── data/
├── notebooks/
│   └── IR_assignment.ipynb
├── assignment_outputs/
│   ├── plots/
│   ├── results.csv
├── README.md
└── requirements.txt

---

## 🚀 Future Improvements

- API deployment (FastAPI)  
- Integration with FAISS / Elasticsearch  
- Real-time search system  
- Model monitoring and retraining  
- Larger transformer models  

---

## 🧠 Key Takeaways

- Hybrid retrieval improves ranking performance  
- Combining lexical + semantic signals is crucial  
- Learning-to-Rank enhances flexibility  
- Evaluation and statistical testing are essential  

---

## 👨‍💻 Author

**Rachakonda Shrutik Sai**  
B.Tech Computer Science, IIIT Dharwad  
Focused on Machine Learning, NLP & Production Systems  

---

⭐ If you found this project useful, consider giving it a star!
