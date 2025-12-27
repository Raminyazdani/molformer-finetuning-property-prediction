# MolFormer Fine-tuning for Molecular Property Prediction

A deep learning project for fine-tuning chemical language models on molecular property prediction tasks.

## Overview

This project demonstrates fine-tuning of pre-trained chemical language models (MolFormer) for molecular property prediction, specifically focusing on lipophilicity prediction using SMILES molecular representations.

## Project Structure

```
molformer-finetuning-property-prediction/
├── notebooks/          # Jupyter notebooks
├── models/            # Trained models and tokenizers
├── data/              # Datasets
├── outputs/           # Predictions and results
├── requirements.txt   # Python dependencies
└── README.md          # This file
```

## Planned Features

- Fine-tuning MolFormer with masked language modeling
- Regression for molecular property prediction
- Influence function-based data selection
- Exploration of various fine-tuning strategies

## Tech Stack

- Python 3.x
- PyTorch
- Transformers (HuggingFace)
- Jupyter Notebook
- Scientific computing libraries (NumPy, Pandas, Scikit-learn)

## Setup

```bash
pip install -r requirements.txt
```

## Status

Project structure established. Implementation in progress.

## License

MIT License

