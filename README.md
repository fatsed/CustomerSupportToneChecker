# Persian Customer Support Tone Checker

A machine learning project for classifying the tone of Persian customer support messages.

The system predicts one of three tone categories:

- `polite`
- `semi_polite`
- `impolite`

This project was developed as a university coursework project to practise Persian text preprocessing, TF-IDF feature extraction, machine learning classification, model evaluation, and interface development with Gradio.

## Project Overview

Customer support messages can express different levels of politeness. The goal of this project is to build a simple NLP pipeline that processes Persian messages and predicts their tone.

The project includes:

- A small Persian customer support dataset
- Persian text preprocessing
- TF-IDF feature extraction
- Training and comparison of multiple classifiers
- Model evaluation
- Saved models for reuse
- A Gradio interface for testing new messages
- Optional Hugging Face API comparison

## Project Structure

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
│   └── 02_tone_detection_api_ui.ipynb
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## Dataset

The dataset is stored in:

```text
dataset/tone_dataset.csv
```

It contains 300 Persian customer support messages divided into three classes:

| Label | Description |
|---|---|
| `polite` | Polite and respectful messages |
| `semi_polite` | Neutral or partly polite messages |
| `impolite` | Impolite or demanding messages |

The dataset contains the following columns:

- `id`: unique message identifier
- `text`: Persian customer support message
- `label`: tone category

The dataset was created for educational purposes and is not intended to represent all real-world customer support conversations.

## Text Preprocessing

The preprocessing pipeline includes:

- Persian text normalization
- Removal of digits and non-Persian characters
- Tokenization
- Stopword removal
- Removal of very short tokens
- Duplicate removal

Stemming and lemmatization were not used because they may alter the structure or meaning of some Persian words.

## Feature Extraction

The project uses TF-IDF to convert processed text into numerical features.

Main configuration:

```python
ngram_range=(1, 2)
min_df=2
max_features=5000
sublinear_tf=True
```

## Machine Learning Models

The following models were trained and compared:

- LinearSVC
- Logistic Regression
- Random Forest
- Decision Tree

Approximate evaluation results:

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| LinearSVC | 0.93 | 0.93 |
| Logistic Regression | 0.93 | 0.93 |
| Random Forest | 0.88 | — |
| Decision Tree | 0.80 | — |

LinearSVC and Logistic Regression achieved the strongest results on the project dataset.

## Gradio Interface

The project includes a Gradio interface that supports:

- Single-message prediction
- Model selection
- Comparison between trained models
- Sample Persian messages
- Right-to-left Persian text display
- Optional Hugging Face API comparison

The interface is available in:

```text
notebooks/02_tone_detection_api_ui.ipynb
```

## Installation

Clone the repository:

```bash
git clone https://github.com/fatsed/CustomerSupportToneChecker.git
cd CustomerSupportToneChecker
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Linux or macOS:

```bash
source .venv/bin/activate
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

## Usage

Open the following notebook:

```text
notebooks/02_tone_detection_api_ui.ipynb
```

Run the cells in order to load the dataset, preprocessing functions, saved models, and Gradio interface.

The notebook can also be opened directly in Google Colab.

## Limitations

This is an educational project and not a production-ready moderation system.

Current limitations include:

- The dataset contains only 300 messages.
- The examples were created for coursework rather than collected from real customer support conversations.
- The `semi_polite` class may overlap with the other two classes.
- Evaluation was performed on a small test set.
- Performance on real-world Persian messages may be lower.
- The model should not be used for automated decisions without human review.

## Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Hazm
- Gradio
- Joblib
- Matplotlib
- Seaborn
- Jupyter Notebook

## License

This project is available under the MIT License.
