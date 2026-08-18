# Complex Network Clustering via Signed Hypergraph Diffusion
This repository contains the code for **Adaptive Signed Hypergraph Diffusion (ASHD)**, a clustering framework for signed hypergraphs.

## Contributions
* Signed Hypergraph Representation
* Higher-Order Relationships
* Adaptive Weighting

## Datasets
The experiments include several graph and hypergraph datasets:
* TRRUST v2:https://www.grnpedia.org/trrust/
* Cora:https://www.kaggle.com/datasets/mrkmakr/cora-dataset
* Bitcoin:https://snap.stanford.edu/data/soc-sign-bitcoin-alpha.html
* MovieLens 100K:https://grouplens.org/datasets/movielens/
Datasets are not included in this repository when redistribution is restricted. Please download the datasets from their original sources and place them in the corresponding directories.

## Experiments
The experiments compare ASHD with several baseline methods, including:
* K-Means
* Spectral Clustering
* HyperGCN

For the TRRUST dataset, ASHD is evaluated using:
* Silhouette Score
* Modularity
* Hyperedge consistency
* GO/pathway enrichment (Using Enricchr:https://maayanlab.cloud/Enrichr/)

## Declaration of generative AI and AI-assisted technologies in the writing process
During the preparation of this work, the authors used Claude 4.5 Sonnet, Grammarly for language editing, clarity improvement, and translation. After using this tool, the authors reviewed and edited the content as needed and take full responsibility for the content of the publication.
