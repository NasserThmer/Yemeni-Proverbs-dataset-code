# 🤖 Generate Explanations using Fine-Tuned AraT5v2

This script uses a fine-tuned [AraT5v2](https://huggingface.co/UBC-NLP/AraT5v2-base-1024) model to generate natural language explanations for Yemeni proverbs.

It reads a test JSON file with proverbs and produces a new JSON file containing generated explanations alongside references.

---

## 📁 File Description

- `generate_explanations.py`: Generation script
- Input: JSON with the following fields:
  - `"id"`: Unique identifier
  - `"proverb"`: The original proverb
  - `"explanation"`: The reference explanation
- Output: JSON file with the same fields plus `"generated_explanation"`

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install transformers datasets torch
```

### 2. Run the script

```bash
python generate_explanations.py \
    --model_path ./arat5v2-finetuned \
    --input_file ./data/test.json \
    --output_file ./sample_data/test_predictions.json
```

---

## 🔁 Generation Settings

- `max_length=128`
- `num_beams=2`
- `no_repeat_ngram_size=2`
- No text normalization is applied to preserve raw dialectal input

---

## 📎 Notes

- The script assumes the model has been fine-tuned using AraT5v2 or compatible Arabic seq2seq models.
- All processing is done using PyTorch with `torch.no_grad()` for safe inference.

---

## 📄 License

MIT License. See the `LICENSE` file for details.
