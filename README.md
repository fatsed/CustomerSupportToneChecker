# Customer Support Tone Checker

A Persian NLP project for detecting customer support tone:

- Classes: `polite`, `semi_polite`, `impolite`
- Language: Persian
- Tools: Python, scikit-learn, Hazm, Gradio, Jupyter/Colab

## Folder structure

- `dataset/tone_dataset.csv` – manually created dataset (300 rows)
- `notebooks/01_build_dataset.ipynb` – build and save dataset
- `notebooks/02_train_model.ipynb` – preprocessing, training, evaluation, API-like function, Gradio UI

## How to run (in Colab)

1. Open `02_train_model.ipynb` in Google Colab.
2. Run all cells (Runtime → Run all).
3. At the end of the notebook, the Gradio UI will launch.
4. Type a new customer message or select a preset example.
5. The app returns:
   - predicted tone label (`polite` / `semi_polite` / `impolite`)
   - Persian tone (`مودبانه` / `نیمه‌مودبانه` / `غیرمودبانه`)
   - cleaned text (after preprocessing)

## Evaluation

- Model: TF-IDF + LinearSVC
- Metrics: Accuracy, F1-score (per class)
- Accuracy: ~ 0.xx  (fill from your run)
