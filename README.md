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
