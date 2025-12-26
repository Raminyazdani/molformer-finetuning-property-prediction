# Project Identity

## Professional Identity

### Display Title
**MolFormer Fine-tuning for Molecular Property Prediction**

### Repo Slug (Suggested)
`molformer-finetuning-property-prediction`

### Tagline
Fine-tuning chemical language models (MolFormer) for molecular lipophilicity prediction using transfer learning and influence-based data selection

### GitHub Description
A deep learning project demonstrating fine-tuning of pre-trained chemical language models (MolFormer) for molecular property prediction. Includes masked language modeling, regression tasks, and influence function-based data selection strategies for enhanced model performance.

### Primary Stack
- Python 3.x
- PyTorch
- Transformers (HuggingFace)
- Jupyter Notebook
- Datasets library
- Pandas, NumPy, Scikit-learn

### Topics/Keywords
- `molecular-property-prediction`
- `chemical-language-models`
- `molformer`
- `transfer-learning`
- `fine-tuning`
- `influence-functions`
- `cheminformatics`
- `deep-learning`
- `pytorch`
- `transformers`
- `lipophilicity-prediction`
- `smiles`

### Problem Statement
Molecular property prediction is crucial in drug discovery and materials science. This project demonstrates how to leverage pre-trained chemical language models (MolFormer) and adapt them to specific molecular property prediction tasks through fine-tuning. The project showcases:

1. **Transfer Learning for Chemistry**: Fine-tuning MolFormer on masked language modeling and regression tasks for lipophilicity prediction
2. **Data Selection Optimization**: Using influence functions to identify the most valuable training samples from external datasets
3. **Model Adaptation Strategies**: Exploring various fine-tuning techniques and data selection methods to improve model performance

### Approach
The project implements a three-part pipeline:
1. Fine-tune MolFormer using masked language modeling (MLM) and regression on the Lipophilicity dataset
2. Apply influence function-based data selection (LiSSA approximation) to select high-impact samples from external datasets
3. Explore alternative data selection strategies and fine-tuning methods

### Inputs
- Molecular structures as SMILES strings
- Lipophilicity dataset from MoleculeNet benchmark (via HuggingFace)
- External molecular datasets for data selection experiments
- Pre-trained MolFormer model (from HuggingFace)

### Outputs
- Fine-tuned MolFormer models (MLM and regression variants)
- Trained tokenizers
- Molecular property predictions (CSV format)
- Model performance metrics and visualizations
- Influence scores for data selection

