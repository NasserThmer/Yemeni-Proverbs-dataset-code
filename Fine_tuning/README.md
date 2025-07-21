# 🧠 Fine-Tuning AraT5v2 for Yemeni Proverbs Explanation

This script fine-tunes the [UBC-NLP/AraT5v2-base-1024](https://huggingface.co/UBC-NLP/AraT5v2-base-1024) model on a dataset of Yemeni proverbs and their explanations. It applies Arabic normalization, tokenization, and sequence-to-sequence training with the Hugging Face `transformers` library.

---

## 📁 File Description

- `train_arat5v2.py`: Fine-tuning script using `Trainer`
- Input: Two JSON files (`train`, `validation`) with fields:
  - `"proverb"`: The original proverb
  - `"explanation"`: The reference explanation in Arabic
- Output: A fine-tuned model saved to the specified directory

---

## 🧹 Preprocessing

The script applies the following:
- Removal of Arabic diacritics
- Character normalization (e.g., `أ` → `ا`, `ة` → `ه`)
- Prepends prompt: `"اشرح المثل اليمني: ..."` before tokenization

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install transformers datasets
```

### 2. Execute the script

```bash
python train_arat5v2.py \
    --train_file data/train.json \
    --val_file data/val.json \
    --model_name UBC-NLP/AraT5v2-base-1024 \
    --output_dir ./arat5v2-finetuned
```

> Ensure both JSON files are lists of dictionaries with `proverb` and `explanation`.

---

## 🛠️ Training Configuration

- Learning rate: 5e-5
- Scheduler: linear
- Epochs: 20
- Batch size: 16
- Early stopping: patience = 2
- Logging & evaluation: per epoch
- Mixed precision: ✅ (fp16)

---

## 📄 License

MIT License. See `LICENSE` file.
