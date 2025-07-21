# Yemeni Proverbs Dataset and Generation Scripts

This repository contains a dataset of Yemeni proverbs and a set of tools and scripts for preprocessing, fine-tuning Arabic language models, generating explanations, and evaluating the results. It is designed to support scientific experiments in proverb interpretation and NLP tasks in Arabic.

---

## 📁 Project Structure and Components

```text
yemeni-proverbs-dataset-code/
├── analysis/               # Scripts and notebooks for statistical analysis and visualization
├── evaluation/             # Scripts to evaluate generated explanations (BLEU, ROUGE, Cosine, etc.)
├── fine_tuning/            # Training scripts for fine-tuning AraT5 or Fanar on the dataset
├── generation/             # Scripts to generate explanations using trained or pretrained models
├── preprocess/             # Scripts for data cleaning and preparing input-target pairs
├── sample_data/            # Example files for quick testing and illustration
├── README.md               # This documentation file
├── requirements.txt        # Python dependencies for the project
└── LICENSE                 # 🔁 (Must be added) License for usage (MIT or CC-BY suggested)
```

---

## ⚙️ Installation

```bash
git clone https://github.com/yourname/yemeni-proverbs-dataset-code.git
cd yemeni-proverbs-dataset-code
pip install -r requirements.txt
```

---

## 🚀 Quick Usage Guide

### 1. Preprocess the Dataset
Prepare the data by normalizing and formatting it for training.

```bash
python preprocess/prepare_dataset.py --input sample_data/sample_proverbs.json --output sample_data/processed.json
```

### 2. Generate Explanations
Use a model like AraT5v2 or Fanar to generate MSA explanations.

```bash
python generation/generate_explanations.py --input sample_data/sample_proverbs.json --output sample_data/generated.json --model arat5
```

### 3. Evaluate Explanations
Compare generated outputs with references using evaluation metrics.

```bash
python evaluation/evaluate_explanations.py --pred sample_data/generated.json --ref sample_data/sample_proverbs.json
```

---

## 🧪 Folder-by-Folder Description

### `analysis/`
- Contains notebooks and scripts for analyzing the dataset:
  - Clustering proverbs using UMAP + HDBSCAN
  - Keyword extraction per cluster
  - Diversity metrics (e.g., Gini index)

### `evaluation/`
- Main file: `evaluate_explanations.py`
- Metrics supported:
  - BLEU, ROUGE, chrF++
  - Cosine Similarity (MiniLM, CAMeL-BERT, Arabic-KW)
  - BERTScore and SAS

### `fine_tuning/`
- Training code for AraT5v2-base-1024 or QCRI/Fanar-1-9B.
- Example script: `train_model.py` (not shown, assumed present)
- Configurable with Huggingface `Seq2SeqTrainingArguments`.

### `generation/`
- Script: `generate_explanations.py`
- Generates text from the proverb input using a seq2seq model.
- Supports both local and Huggingface-hosted models.

### `preprocess/`
- Script: `prepare_dataset.py`
- Normalizes Arabic text, removes diacritics, and formats pairs for training or inference.

### `sample_data/`
- `sample_proverbs.json`: Mini set (10–20 examples) for testing.
- `train.json`, `val.json`: ⛔ Must be downloaded from Zenodo (DOI link to be added).
- `test_predictions_Yemni_proverbs.json`: Output file for evaluation.

---

## 🔬 Scientific Context

This repository supports a submission to *Scientific Data* (Nature), in the “Text and Speech Corpora” collection. It is built with the goal of advancing Arabic NLP by providing:

- A culturally rich and annotated dataset
- Tools for explanation generation
- Automatic and statistical validation metrics

---

## 📜 License

> ⚠️ *A LICENSE file should be added — MIT is recommended for academic reuse.*

---

## 📬 Contact

For questions or contributions:
- Nasser Saleh — nasser@example.com
