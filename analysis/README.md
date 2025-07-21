# 🧩 Thematic Clustering of Yemeni Proverbs

This script performs **unsupervised semantic clustering** of Yemeni proverbs using modern Arabic language embeddings, dimensionality reduction, and density-based clustering.

It uses:
- ✅ Arabic-Triplet-Matryoshka-V2 for generating sentence embeddings
- ✅ UMAP for dimensionality reduction
- ✅ HDBSCAN for cluster discovery
- ✅ Matplotlib for visualizing clusters
- ✅ Keyword extraction to summarize each cluster thematically

---

## 📁 File Description

- `cluster_proverbs.py`: The main Python script for the full pipeline.
- `data/Yemeni_proverbs.json`: Proverbs dataset (downloaded automatically if not present).
- Output: UMAP scatter plot + printed top keywords per cluster.

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install pandas numpy sentence-transformers umap-learn hdbscan matplotlib
```

### 2. Run the script

```bash
python cluster_proverbs.py
```

The script will:
- Download the dataset (if not found locally)
- Compute embeddings using the Arabic-Triplet-Matryoshka-V2 model
- Reduce dimensions using UMAP
- Cluster the proverbs using HDBSCAN
- Visualize the clusters with matplotlib
- Print top 10 keywords for each cluster

---

## 📊 Output

- 📈 A 2D scatter plot of clustered proverbs (UMAP visualization)
- 📋 Top 10 most frequent keywords per cluster (printed in terminal)
- 🗃️ Cluster labels added to the dataset (`df["cluster"]`)

---

## 📎 Notes

- Replace the placeholder `DATA_URL` in the script with your actual Zenodo URL.
- Cluster `-1` represents noise (proverbs not assigned to any cluster).
- You may save the figure to file by adding:  
  `plt.savefig("figures/clustering_umap.png", dpi=300)`

---

## 📄 License

This code is open-source and available under the MIT License. See the `LICENSE` file for details.

---

## 📬 Citation (if used in research)

```bibtex
@misc{yemeni_proverbs_2025,
  author       = {Your Name and Coauthors},
  title        = {Yemeni Proverbs Dataset: Semantic Clustering and Explanation},
  year         = {2025},
  url          = {https://zenodo.org/record/XXXXXXX},
  note         = {Preprint or dataset DOI}
}
```
