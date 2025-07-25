# Yemeni Proverbs Dataset

This folder contains the finalized version of the **Yemeni Proverbs Dataset**, a structured collection of traditional Yemeni proverbs along with their meanings and metadata. The dataset is intended for use in Arabic Natural Language Processing (NLP), figurative language modeling, cultural reasoning, and dialectal studies.

## 📦 Contents

- `Yemeni_proverbs.json`: A JSON file containing 5,252 unique Yemeni proverbs, each annotated with:
  - `id`: Unique numeric identifier.
  - `proverb`: The proverb in its original Yemeni Arabic form.
  - `explanation`: A human-authored explanation in Modern Standard Arabic (MSA).
  - `city`: Geographic origin if available; otherwise `"None"`.
  - `source`: Book or resource from which the proverb was extracted.
  - `url`: Web source if applicable.

## 💡 Example Entry

```json
{
  "id": 1,
  "proverb": "الكسل ابن عم الفشل إبن هات إعطي",
  "explanation": "أي أنه يكل فيفشل ثم يعود فيسأل قوت يومه ممن يتفضل عليه...",
  "city": "None",
  "source": "كتاب: الثروة اليمنية من الأمثال الشعبية",
  "url": "Non"
}
```

## 🧑‍🏫 Dataset Purpose

This dataset serves multiple research goals:

- Modeling Arabic figurative expressions in generative tasks.
- Exploring dialectal variation in proverb formulation.
- Evaluating language models' ability to reason culturally and semantically.
- Supporting automatic explanation generation and figurative language classification.

## 🏷️ Licensing and Citation

The dataset is distributed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.  
If you use this dataset, please cite the corresponding paper:

> Saleh, N. et al. (2025). A benchmark dataset of Yemeni proverbs with MSA explanations for figurative language modeling. *Scientific Data*. [DOI link pending]

## 📬 Contact

For questions, corrections, or collaboration requests, please contact:  
📧 `nassersaleh.cs [at] example.com`
