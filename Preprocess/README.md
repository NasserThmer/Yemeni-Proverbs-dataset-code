# 🧹 Preprocess Yemeni Proverbs Dataset

This script prepares a JSON dataset of Yemeni proverbs and explanations for training by:
- Removing Arabic diacritics
- Normalizing letter variations
- Formatting the input as a prompt
- Tokenizing the data using an Arabic seq2seq tokenizer

---

## 📁 File Description

- `prepare_dataset.py`: Preprocess and tokenize script
- Input: Raw JSON file with fields:
  - `"proverb"`: Raw proverb string
  - `"explanation"`: Raw explanation
- Output: JSON file with fields:
  - `"input"`: Prompted and tokenized text
  - `"labels"`: Tokenized explanation (with padding masked)

---

## 🧠 Normalization Applied

- Remove tashkeel (diacritics)
- Normalize:
  - `أ`, `آ`, `إ` → `ا`
  - `ة` → `ه`
  - `ى` → `ي`
  - `ؤ`, `ئ` → `و`, `ي`

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install transformers datasets
```

### 2. Run the script

```bash
python prepare_dataset.py \
    --dataset_path ./data/raw_proverbs.json \
    --tokenizer_name UBC-NLP/AraT5v2-base-1024 \
    --output_path ./data/tokenized_proverbs.json
```

---

## 📎 Notes

- The output is suitable for training with Hugging Face `Trainer`.
- Tokenization replaces padding tokens in labels with `-100` to exclude them from loss computation.

---

## 📄 License

MIT License. See `LICENSE` file for terms.
