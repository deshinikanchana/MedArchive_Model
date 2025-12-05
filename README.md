# 🏥 Clinical Document Classification System
*A Production-Grade Machine Learning Pipeline for Healthcare Document Routing*

This project develops a **scalable ML system** that classifies clinical transcriptions into **13 medical specialties**, helping hospitals automate document routing, reduce errors, and accelerate billing workflows.

> Built according to the **ITS 2130: Machine Learning – Group Project Specification** for the fictional healthcare client **MedArchive Solutions**.

---

## 📌 Project Overview

### 🎯 Objective
To design and deploy a machine learning model capable of automatically routing clinical documents to the correct medical specialty department.

### 🏛️ Business Impact
- Eliminates slow, error-prone manual document triage
- Improves turnaround times for billing and patient follow-up
- Saves administrative labor costs
- Scales to thousands of documents per day

---

## 📦 Dataset Information
- Dataset: **HPE-AI Medical Cases Classification Dataset**
- Total records: **2,460 clinical transcriptions**
- Target label: **medical_specialty**
- Contains unstructured physician notes, diagnoses, treatment plans and discharge summaries.

---

## 🔍 Phase 1: ML Development

### 📊 1) Exploratory Data Analysis (EDA)
Performed:
- Document length distribution
- Class imbalance visualization
- Word frequency and word clouds per specialty
- Keyword correlation insights

### 🧹 2) Text Preprocessing Pipeline
Implemented using **`TfidfVectorizer`**:
- Lowercasing & stop-word removal
- Tokenization and vectorization via TF-IDF
- Handles high-dimensional medical vocabulary

### 🧠 3) Predictive Modeling
- Model: **Softmax Regression (Multinomial Logistic Regression)**
- Framework: Scikit-learn
- Validation: Cross-validation + Hyperparameter tuning
- Output: **Single Scikit-learn Pipeline** (Preprocessing + Model)

### 🧪 4) Rigorous Model Evaluation
Metrics analyzed:
- Confusion Matrix (Heatmap)
- Accuracy Limitations
- Per-Class Precision, Recall & F1-Score
- Interpretation based on clinical business risk (e.g., false negatives in Oncology)

### 🌀 5) Unsupervised Clustering
Applied **k-Means Clustering** to identify hidden groups such as:
- Surgical cases
- Pulmonary cases
- Diagnostic reports  
Helps reveal potential sub-specialty segmentation.

---

## ☁️ Phase 2: Production Deployment

### 🚀 Deployment Pipeline (Vertex AI)
Steps completed:
1. Exported final ML Pipeline (`joblib`)
2. Uploaded artifacts to **Google Cloud Storage (GCS)**
3. Registered model using **Vertex AI Model Registry**
4. Served model via built-in **Scikit-Learn container**
5. Tested live REST inference response

📌 **Output:** Predicts a medical specialty from raw clinical transcription text.

---

## 📁 Project Structure

```
├── notebooks/
│ ├── 1_eda_and_preprocessing.ipynb
│ ├── 2_classification_modeling.ipynb
│ ├── 3_clustering_analysis.ipynb
│
├── artifacts/
│ └── clinical_pipeline.joblib # Production model
│
├── requirements.txt
└── README.md
```


---

## 🛠️ Technologies Used

| Category | Tools |
|----------|-------|
| Machine Learning | Scikit-Learn, TF-IDF, Softmax Regression, k-Means |
| Programming | Python |
| Visualization | matplotlib, seaborn, wordcloud |
| Deployment | Google Cloud Storage, Vertex AI |
| Packaging | joblib, Scikit-learn Pipelines |

---

## 📌 Future Improvements
- Upgrade to contextual embeddings (BERT, BioClinicalBERT)
- Specialty-specific confidence thresholds
- Add domain-specific clinical corpus for vocabulary expansion
- Integrate feedback loop for continuous model improvement

---

### 👥 Authors
- *Deshini Kanchana* (Intern Software Engineer)
- Group Members: *(Nadeesha Thejangani, Chami savishka , Imesha Udani)*

---


