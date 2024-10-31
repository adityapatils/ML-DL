# Gene-Phenotype Causality Analysis: Uncovering Relationships Using Embeddings

## Table of Contents
1. [Project Overview](#project-overview)
2. [Objectives](#objectives)
3. [Key Concepts](#key-concepts)
4. [Methodology](#methodology)
    - [Dataset Preparation](#dataset-preparation)
    - [Dimensionality Reduction](#dimensionality-reduction)
    - [Vector Analysis](#vector-analysis)
    - [Clustering Analysis](#clustering-analysis)
5. [Datasets](#datasets)
6. [Results and Insights](#results-and-insights)
7. [Technologies Used](#technologies-used)


---

## Project Overview
This project aims to explore the relationships between genes and phenotypes (observable traits) by analyzing their embeddings (numerical vector representations). Specifically, we look into how causal and non-causal genes associated with each phenotype can be differentiated based on vector analysis, dimensionality reduction, and clustering techniques. The end goal is to derive insights that may help identify potential genetic causes for specific traits, contributing to advancements in genetic research.

## Objectives
The key objectives of this project are to:
1. Map phenotypes to their associated causal and non-causal genes.
2. Apply dimensionality reduction techniques for visualizing the relationship between genes and phenotypes.
3. Conduct vector analysis to explore relationships and potential causality.
4. Use clustering methods to identify groups of genes and phenotypes that may suggest causal relationships.

---

## Key Concepts
### 1. **Phenotype and Genotype Relationship**
   - Understand the connection between observable traits (phenotypes) and underlying genetic makeup (genotype).

### 2. **Mapping Causal and Non-Causal Genes**
   - Create a dataset that maps each phenotype to its causal gene(s) and to other non-causal genes, enabling a labeled dataset for relationship analysis.

### 3. **Dimensionality Reduction**
   - Use techniques like Principal Component Analysis (PCA) to reduce the number of dimensions in the data, simplifying complex datasets for visualization and interpretation.

### 4. **Vector Analysis**
   - Analyze and manipulate embeddings to derive new vectors that represent relationships between phenotypes and genes.

### 5. **Cosine Similarity**
   - Measure similarity between vectors (embeddings of genes and phenotypes) to assess how closely they are related.

### 6. **Clustering Techniques**
   - Use clustering algorithms like K-means and DBSCAN to identify patterns and potential causal relationships within gene-phenotype data.

### 7. **Data Visualization**
   - Apply tools like Plotly to create interactive visualizations, enhancing the communication of complex relationships to a broader audience.

---

## Methodology

### Dataset Preparation
- **Mapping Phenotypes to Genes:** Each phenotype is associated with multiple genes, including one causal gene and several non-causal genes. A new dataset is created where each phenotype is mapped to both its causal and non-causal genes, with labels indicating causality.

### Dimensionality Reduction
- **Principal Component Analysis (PCA):** Dimensionality reduction is applied to the high-dimensional gene and phenotype embeddings to simplify the data. This step enables visualization of gene-phenotype relationships in a two-dimensional space.

### Vector Analysis
- **Embedding Manipulation:** We calculate new vectors representing relationships between genes and phenotypes by performing mathematical operations, such as subtraction of embeddings.
- **Cosine Similarity Calculation:** The cosine similarity metric is calculated between phenotype and gene embeddings to quantify the closeness of these relationships.

### Clustering Analysis
- **K-means and DBSCAN Clustering:** Clustering methods are applied to group genes and phenotypes based on their embeddings. The aim is to identify clusters that may suggest causal relationships.
- **Evaluation of Clustering Results:** We assess the quality of clusters to see if any meaningful grouping emerges, which could indicate potential causal relationships.

---

## Datasets

The dataset for this project can be downloaded from [Zenodo](https://zenodo.org/records/11391053). Paths to the required files are relative to the `zenodo_directory` inside the downloaded zip file. Use only the specified files for this analysis:

- **Phenotypes and Genes**: Traits or conditions and their associated genes. Each phenotype has one causal gene.
  - **File**: `zenodo_directory/data/benchmark_datasets/opentargets_step2.for_llm.tsv`

- **Ground Truth**: Causal gene for each phenotype, ordered consistently with the above file.
  - **File**: `zenodo_directory/data/benchmark_datasets/opentargets_step2.labels`

- **Features**: 3072-dimensional embedding vectors for all phenotypes and genes, providing features for analysis.
  - **Files**:
    - `zenodo_directory/data/helper_datasets/gene_embeddings.csv`
    - `zenodo_directory/data/helper_datasets/phenotype_embeddings.csv`

### Creating a Unique Dataset

1. **Hash Your Name**: Convert your name to a hash value by removing spaces and using a consistent case (e.g., `firstnameLastname`). This will serve as a unique identifier.
2. **Use the Hash as a Seed**: Use this hash value as a seed for random sampling, ensuring you consistently get the same subset of data.
3. **Sample 500 Phenotypes**: Using the seed, randomly sample 500 phenotypes from the data. This subset will form the basis of your analysis.
4. **Document the Hash**: Include this hash value in your project submission to validate the unique dataset.

---

## Results and Insights
- **Dimensionality Reduction Results:** Visualization of PCA-reduced embeddings reveals spatial groupings between genes and phenotypes, highlighting potential areas where causal genes may cluster with their related phenotypes.
- **Cosine Similarity Findings:** High similarity scores indicate stronger relationships, allowing us to rank potential causal genes for each phenotype.
- **Clustering Insights:** Clustering analysis results suggest distinct groups, which may be useful for further hypothesis generation and experimental validation of causal relationships.

---

## Technologies Used
- **Python**: The core language for data manipulation, analysis, and visualization.
- **Pandas and NumPy**: For data handling and numerical operations.
- **scikit-learn**: For implementing PCA, K-means, DBSCAN, and other machine learning techniques.
- **Plotly**: For interactive and visually appealing plots.
- **SciPy**: For calculating cosine similarity, a metric used to assess relationships between vectors.

---

## Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or any Python IDE
- Install the required libraries:
  ```bash
  pip install pandas numpy scikit-learn plotly scipy
