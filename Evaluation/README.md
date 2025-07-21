# 📊 Evaluation Metrics for Generated Explanations

This script evaluates the quality of generated explanations against reference explanations using a rich set of automatic metrics designed for Arabic language processing.

It supports the following metrics:
- 🟦 BLEU (with smoothing)
- 🟥 ROUGE-1, ROUGE-2, ROUGE-L
- 🟨 BERTScore (Arabic)
- 🟪 Cosine similarity using:
  - MiniLM
  - CAMeL-BERT
  - Arabic-KW-Mdel
- 🟧 Semantic Answer Similarity (SAS) using Arabic-SBERT-100K
- 🟩 chrF++ from SacreBLEU

---

## 📁 File Description

- `eval_metrics.py`: The main evaluation script
- Input: JSON file with fields:
  - `reference_explanation`
  - `generated_explanation`
- Output: The same JSON file updated with metric scores + average printout to console

---

## 🛠️ Installation

Install the required Python packages:

```bash
pip install pandas numpy tqdm nltk rouge-score bert-score sacrebleu sentence-transformers
```

> Also run:
```python
import nltk
nltk.download('punkt')
```

---

## 🚀 How to Run

```bash
python eval_metrics.py --file path/to/generated_outputs.json
```

- The input file must be a list of dictionaries with two fields:
  - `"reference_explanation"`: The gold explanation
  - `"generated_explanation"`: The predicted/generated explanation

- The script adds new metric columns and overwrites the file (if `save=True`)

---

## 📊 Output

- Per-example scores added to JSON
- Printed average metrics:
  - BLEU, ROUGE-1/2/L
  - Cosine (3 models)
  - SAS, BERTScore, chrF++

---

## 📄 License

This code is licensed under the MIT License.
