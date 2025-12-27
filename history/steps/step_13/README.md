# MolFormer Fine-tuning for Molecular Property Prediction

Fine-tuning chemical language models (MolFormer) for molecular lipophilicity prediction using transfer learning and influence-based data selection.

## Overview

This project demonstrates how to leverage pre-trained chemical language models (MolFormer) and adapt them to specific molecular property prediction tasks through fine-tuning. The project showcases transfer learning techniques for chemistry, influence function-based data selection, and various model adaptation strategies.

## Features

- Fine-tuning MolFormer using masked language modeling (MLM) and regression
- Influence function-based data selection using LiSSA approximation
- Exploration of alternative data selection and fine-tuning strategies
- End-to-end pipeline from model training to prediction

## Project Structure

```
molformer-finetuning-property-prediction/
├── notebooks/                                    # Jupyter notebooks
│   ├── mlm_regression_training.ipynb            # MLM + regression fine-tuning
│   ├── influence_based_selection.ipynb          # Influence function data selection
│   └── exploration_finetuning_methods.ipynb     # Alternative strategies
├── models/                                       # Trained models and tokenizers
│   ├── mlm_finetuned_molformer/                 # Fine-tuned model
│   └── mlm_finetuned_tokenizer/                 # Fine-tuned tokenizer
├── data/                                         # Dataset directory
├── outputs/                                      # Predictions and results
├── requirements.txt                              # Python dependencies
├── LARGE_FILES.md                               # Large file management guide
└── README.md                                    # This file
```

## Setup

### Prerequisites

- Python 3.8+
- CUDA-capable GPU (recommended)

### Installation

```bash
# Clone repository
git clone https://github.com/yourusername/molformer-finetuning-property-prediction.git
cd molformer-finetuning-property-prediction

# Install dependencies
pip install -r requirements.txt
```

## Usage

### Notebook Execution Order

1. **mlm_regression_training.ipynb**: Fine-tune MolFormer on lipophilicity dataset
2. **influence_based_selection.ipynb**: Apply influence functions for data selection
3. **exploration_finetuning_methods.ipynb**: Explore alternative fine-tuning strategies

### Running Notebooks

```bash
jupyter notebook
```

Then navigate to the `notebooks/` directory and open the desired notebook.

## Datasets

- **Lipophilicity Dataset**: Loaded from HuggingFace MoleculeNet benchmark
- **External Datasets**: Place in `data/` directory (see notebooks for format requirements)

## Outputs

The project generates:
- Fine-tuned MolFormer models in `models/`
- Molecular property predictions in `outputs/`
- Training metrics and visualizations

## Troubleshooting

**CUDA Out of Memory**: Reduce batch size in training notebooks
**Import Errors**: Ensure all dependencies are installed via requirements.txt
**Dataset Loading**: Verify internet connection for HuggingFace dataset downloads

## References

- MolFormer: https://arxiv.org/abs/2106.09553
- MoleculeNet: https://arxiv.org/abs/1703.00564
- Influence Functions: https://arxiv.org/abs/1703.04730
