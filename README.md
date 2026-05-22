# 💬 Customer Support Tone Checker (Persian)

A small machine learning project for detecting the tone of Persian customer support messages.

The model classifies each message into one of three tone categories:

- `polite`
- `semi_polite`
- `impolite`

This project was built as a university project and as practice for working with Persian text preprocessing, TF-IDF features, machine learning classifiers, and a simple Gradio interface.
---

## 📌 Project Overview

Customer support messages can have different tones. Some messages are polite, some are neutral or semi-polite, and some may sound impolite.

The goal of this project is to build a simple text classification pipeline that can analyze Persian customer support messages and predict their tone.

This project includes:

- Persian text preprocessing
- TF-IDF feature extraction
- Training and comparing multiple machine learning models
- Model evaluation
- A simple Gradio interface for testing messages
---

## 📁 Project Structure

CustomerSupportToneChecker/

- dataset/
  - tone_dataset.csv

- models/
  - tfidf_vectorizer.pkl
  - svm_linearsvc.pkl
  - logistic_regression.pkl
  - random_forest.pkl
  - decision_tree.pkl

- notebooks/
  - 01_build_dataset.ipynb
  - 02_ToneDetection_api_ui.ipynb

- README.md
---

## 🗂️ Dataset

The dataset is located in:

`dataset/tone_dataset.csv`

It contains 300 Persian customer support messages.

The messages are divided into three labels:

- `polite`: polite customer support message
- `semi_polite`: partly polite or neutral message
- `impolite`: impolite customer support message

Dataset columns:

- `id`: unique message ID
- `text`: Persian customer support message
- `label`: tone category
---

## 🧹 Text Preprocessing

The preprocessing step includes:

- Normalizing Persian text
- Removing non-Persian characters
- Removing digits
- Tokenizing text
- Removing stopwords
- Removing very short tokens

I did not use stemming or lemmatization in this project because they can sometimes change the structure or meaning of Persian words.
---

## 🔢 Feature Extraction

The project uses TF-IDF to convert Persian text into numerical features.

Main TF-IDF settings:

- `ngram_range=(1, 2)`
- `min_df=2`
- `max_features=5000`
- `sublinear_tf=True`

The saved TF-IDF vectorizer is stored in:

`models/tfidf_vectorizer.pkl`
---

## 🤖 Machine Learning Models

The following machine learning models were trained and compared:

- SVM / LinearSVC
- Logistic Regression
- Random Forest
- Decision Tree

Performance summary:

- SVM / LinearSVC: Accuracy around 0.93, Macro F1 around 0.93
- Logistic Regression: Accuracy around 0.93, Macro F1 around 0.93
- Random Forest: Accuracy around 0.88
- Decision Tree: Accuracy around 0.80

SVM and Logistic Regression performed best in this project.
---

## 🖥️ Gradio Interface

This project includes a simple Gradio interface for testing Persian customer support messages.

The interface supports:

- Single message prediction
- Model selection
- Comparing model outputs
- Sample Persian messages
- Right-to-left Persian text display
- Optional Hugging Face API integration

The Gradio interface is available inside:

`notebooks/02_ToneDetection_api_ui.ipynb`

---

## 🚀 How to Run

### 1. Clone the repository

`git clone https://github.com/fatsed/CustomerSupportToneChecker.git`

### 2. Go to the project folder

`cd CustomerSupportToneChecker`

### 3. Install the required libraries

`pip install pandas scikit-learn hazm gradio joblib`

### 4. Open the notebook

Open this notebook:

`notebooks/02_ToneDetection_api_ui.ipynb`

Then run the cells to load the models and test the Gradio interface.

---

## ✨ Example Use

You can enter a Persian customer support message, and the model will predict whether the tone is:

- polite
- semi-polite
- impolite

This can be useful as a simple practice project for learning text classification and basic NLP concepts.
---

## ⚠️ Notes

This is a small educational project and not a production-level system.

Some limitations:

- The dataset is small.
- The dataset was created for practice.
- The `semi_polite` class can sometimes overlap with both `polite` and `impolite`.
- The model may not generalize well to real-world customer support data without a larger and more diverse dataset.
---

## 📚 What I Learned

Through this project, I practiced:

- Working with Persian text data
- Building a simple NLP pipeline
- Using TF-IDF for text classification
- Training different machine learning models
- Comparing model performance
- Saving and loading trained models
- Creating a simple Gradio demo
---

## 🛠️ Tech Stack

- Python
- Pandas
- Scikit-learn
- Hazm
- Gradio
- Joblib
- Jupyter Notebook
