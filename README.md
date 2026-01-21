# MetaX_Cirrhosis_Detection
Non-Invasive Liver Cirrhosis Detection Using Metagenomics


# Phylogenetic Graph-Based Liver Cirrhosis Detection

A machine learning framework for non-invasive detection of liver cirrhosis using human gut metagenomics data and phylogenetic graph embeddings.

## 📋 Overview

Liver cirrhosis affects 1-2% of the global population, with late diagnosis significantly increasing mortality risk. This project develops a non-invasive diagnostic tool using gut microbiome data to detect cirrhosis, leveraging phylogenetic relationships among microbial taxa through graph-based learning.

## 🎯 Key Features

- **Non-invasive Detection**: Stool sample-based diagnosis eliminating need for liver biopsy
- **Phylogenetic Graph Construction**: Encodes evolutionary relationships among microbial taxa
- **Graph Embeddings**: Node2Vec for capturing taxonomic hierarchies
- **High Performance**: 93% ROC-AUC with 85.8% accuracy
- **Interpretable Results**: SHAP analysis for clinical decision support
- **Compositional Data Handling**: rCLR transformation and matrix completion

## 🔬 Methodology

### Data Preprocessing
1. **Dataset**: Human gut metagenomics data from Kaggle (N=232 samples)
2. **Compositional Transformation**: Centered log-ratio (rCLR) normalization
3. **Sparsity Handling**: Matrix completion for missing values

### Model Architecture
1. **Phylogenetic Graph Construction**: Directed taxonomic graph (kingdom to species)
2. **Graph Embedding**: Node2Vec for learning taxon representations
3. **Patient-Level Aggregation**: Abundance-weighted sum pooling
4. **Classification**: XGBoost with optimized hyperparameters

### Validation
- 5-fold stratified cross-validation
- Train-test generalization gap < 7%
- SHAP-based feature importance analysis

## 📊 Results

| Metric | Score | Clinical Interpretation |
|--------|-------|------------------------|
| **ROC-AUC** | 0.93 ± 0.03 | Strong discrimination between cirrhosis and healthy controls |
| **Precision** | 87.77% ± 4.3% | Reduces false positives, limiting unnecessary invasive follow-up |
| **Recall** | 83.88% ± 6.7% | Detects most disease cases |
| **Accuracy** | 85.75% ± 4.0% | Consistent performance across validation folds |

## 🛠️ Technology Stack

**Languages & Libraries:**
- Python
- Scikit-learn
- XGBoost
- Node2Vec
- SHAP
- Pandas
- NumPy

**Techniques:**
- Graph Embeddings
- rCLR Transformation
- Matrix Completion
- Stratified Cross-Validation
- Hyperparameter Tuning
- Compositional Data Analysis
