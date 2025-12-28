# MolFormer Fine-tuning for Molecular Property Prediction

A deep learning project for fine-tuning chemical language models (MolFormer) on molecular property prediction tasks.

## Overview

This project demonstrates transfer learning with pre-trained chemical language models for lipophilicity prediction.

## Repository Structure

```
molformer-finetuning-property-prediction/
├── notebooks/          # Jupyter notebooks
├── models/            # Trained models and tokenizers
│   └── mlm_finetuned_molformer/  # Fixed: Corrected path name
├── data/              # Dataset directory
├── outputs/           # Results and predictions
├── requirements.txt   # Python dependencies
└── README.md         # This file
```

## Setup / Installation

### Prerequisites
- Python 3.8 or higher
- CUDA-capable GPU (recommended)
- 8GB+ RAM

### Installation Steps

1. Clone the repository:
```bash
git clone https://github.com/Raminyazdani/molformer-finetuning-property-prediction.git
cd molformer-finetuning-property-prediction
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Start Jupyter Notebook:
```bash
jupyter notebook
```


## Development Notes

- Initial batch size of 32 is causing CUDA out of memory errors during training
- Will need to reduce batch size in next commit
