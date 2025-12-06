# 🧠 Customer Support Tone Checker (Persian)

A mini **NLP project** for detecting the **tone of Persian customer support messages**.  
The system classifies each message into three classes:

- 🟢 `polite`
- 🟡 `semi_polite`
- 🔴 `impolite`

It includes:

- A full **NLP pipeline** (preprocessing → TF-IDF → ML models → evaluation)
- Multiple **classifiers** (SVM, Logistic Regression, Random Forest, Decision Tree)
- A **Gradio UI** with multi-tabs and optional **HuggingFace API** integration

---

## 📂 Project Structure

Example layout:

```text
CustomerSupportToneChecker/
├── dataset/
│   └── tone_dataset.csv
├── models/
│   ├── tfidf_vectorizer.pkl
│   ├── svm_linearsvc.pkl
│   ├── logistic_regression.pkl
│   ├── random_forest.pkl
│   └── decision_tree.pkl
├── notebooks/
│   ├── 01_build_dataset.ipynb 
│   └── 02_ToneDetection_api_ui.ipynb    ← main notebook
├── app/
│   └── gradio_tone_checker.py           ← optional standalone app
├── README.md
```
## 🧾 Dataset

- Location: `dataset/tone_dataset.csv`  
- Total samples: 300  
- Balanced across three labels: `polite`, `semi_polite`, `impolite`

Columns:

| column | explanation |
|--------|-------------|
| id     | unique ID   |
| text   | Persian message |
| label  | tone class |

---

## 🧹 Preprocessing

Steps (Hazm + regex):

- Normalize Persian text  
- Remove non-Persian characters & digits  
- Tokenize  
- Remove stopwords & short tokens  
- *No stemming / lemmatization* (breaks Persian morphology)

---

## ✨ TF-IDF Features

- Unigrams + bigrams  
- `min_df = 2`  
- `max_features = 5000`  
- `sublinear_tf = True`  

Vectorizer saved as:


---

## 🤖 Models

Trained models:

- SVM (LinearSVC)  
- Logistic Regression  
- Random Forest  
- Decision Tree  

Saved inside `/models/`.

Performance (summary):

| Model | Accuracy | Macro F1 |
|-------|----------|----------|
| SVM | ~0.93 | ~0.93 |
| Logistic Regression | ~0.93 | ~0.93 |
| Random Forest | 0.88 | — |
| Decision Tree | 0.80 | — |

---

## 🖥️ Gradio UI

Available inside:


Features:

- RTL Persian interface  
- Model selection  
- Single prediction  
- Compare models  
- Sample messages  
- Optional HuggingFace API integration  

---

## 🚀 Usage

### 1) Clone the repo
```bash
git clone https://github.com/fatsed/CustomerSupportToneChecker.git
cd CustomerSupportToneChecker

📬 Notes

Dataset is small (300 samples) → for educational/demo use

Semi-polite class may overlap with polite/impolite

Works fully offline; HuggingFace integration is optional
