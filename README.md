# Complex Network Clustering via Signed Hypergraph Diffusion
This repository contains the code for **Adaptive Signed Hypergraph Diffusion (ASHD)**, a clustering framework for signed hypergraphs.

## Key Features
* **Signed Hypergraph Representation:** Models both positive and negative relationships.
* **Higher-Order Relationships:** Preserves group-level interactions using hyperedges instead of reducing them to pairwise edges.
* **Adaptive Weighting:** Dynamically updates hyperedge weights during diffusion.
* **Diffusion-Based Clustering:** Learns node representations through iterative signed hypergraph diffusion.
* **Clustering Evaluation:** Supports standard clustering metrics and biological enrichment analysis.

## Repository Structure

```text
ASHD/
├── README.md
├── src/
│   ├── ashd.py
│   └── utils.py
├── experiments/
│   ├── trrust.py
│   ├── cora.py
│   └── epinions.py
├── notebooks/
│   └── trrust_clustering.ipynb
├── figures/
├── results/
├── data/
└── requirements.txt
```

## Datasets

The experiments include several graph and hypergraph datasets:

* **TRRUST v2** – transcription factor–target gene regulatory network
* **Cora** – citation network
* **Epinions** – signed social network
* **MovieLens 100K** – user–movie rating data

Raw datasets are not included in this repository when redistribution is restricted. Please download the datasets from their original sources and place them in the corresponding `data/` directories.

## Method Overview

Given a signed hypergraph

[
H=(V,E,\sigma),
]

where (V) is the vertex set, (E) is the hyperedge set, and (\sigma) represents the sign of each hyperedge, ASHD iteratively performs signed hypergraph diffusion and adaptive weight updates.

The node representation is updated through the adaptive diffusion operator:

[
X^{(t+1/2)} = P^{(t)}X^{(t)},
]

followed by adaptive updates of the hyperedge weights.

The learned node representations are then used for clustering.

## Experiments

The experiments compare ASHD with several baseline methods, including:

* K-Means
* Spectral Clustering
* HyperGCN
* Other graph and hypergraph clustering methods

For the TRRUST dataset, ASHD is evaluated using clustering quality and biological relevance, including:

* Silhouette Score
* Adjusted Rand Index (ARI)
* Normalized Mutual Information (NMI)
* Hyperedge consistency
* GO/pathway enrichment

## TRRUST Results

On the TRRUST transcriptional regulatory network, ASHD produces clearly separated clusters in the learned embedding space.

The adaptive weighting mechanism causes closely related vertices to move closer together, resulting in clearer cluster boundaries. Several top transcription factors, including **AR, EZH2, TP53, ESR1, and POU5F1**, show significant enrichment and strong functional consistency with genes within their corresponding clusters.

The clustering achieves a **silhouette score greater than 0.5** and significantly outperforms the random permutation baseline (**permutation test, (p_{\mathrm{perm}} < 0.01)**).

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/ASHD.git
cd ASHD
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

## Running the Experiments

For example, to run the TRRUST experiment:

```bash
python experiments/trrust.py
```

For notebook-based experiments:

```bash
jupyter notebook notebooks/trrust_clustering.ipynb
```

Please make sure the required dataset files are placed in the expected `data/` directory before running the experiments.

## Reproducibility

The experiments use fixed random seeds where applicable. Detailed experimental parameters, dataset preprocessing procedures, and evaluation settings are provided in the corresponding experiment scripts and notebooks.

## Citation

If you use this code or ASHD in your research, please cite the corresponding paper:

```bibtex
@article{YOUR_CITATION,
  title  = {Adaptive Signed Hypergraph Diffusion},
  author = {Your Name},
  year   = {2026}
}
```

## Contact

For questions regarding the implementation or experiments, please contact the authors.
