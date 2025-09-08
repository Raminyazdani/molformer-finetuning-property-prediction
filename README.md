# MolFormer Fine-tuning for Molecular Property Prediction

Fine-tuning chemical language models (MolFormer) for molecular lipophilicity prediction using transfer learning and influence-based data selection.

## Overview

This project demonstrates how to leverage pre-trained chemical language models (MolFormer) and adapt them to specific molecular property prediction tasks through fine-tuning. The project showcases transfer learning techniques for chemistry, influence function-based data selection, and various model adaptation strategies to improve predictive performance on molecular datasets.

**Key Features:**
- Fine-tuning MolFormer using masked language modeling (MLM) and regression
- Influence function-based data selection using LiSSA approximation
- Exploration of alternative data selection and fine-tuning strategies
- End-to-end pipeline from model training to prediction

## Problem & Approach

Molecular property prediction is crucial in drug discovery and materials science. Traditional approaches require extensive feature engineering, but chemical language models can learn molecular representations directly from SMILES strings.

**This project demonstrates:**
1. **Transfer Learning for Chemistry**: Adapting pre-trained MolFormer to lipophilicity prediction
2. **Smart Data Selection**: Using influence functions to identify high-impact training samples
3. **Model Optimization**: Exploring various fine-tuning techniques for improved performance

**Approach:**
- Start with pre-trained MolFormer from HuggingFace
- Fine-tune using masked language modeling and regression on Lipophilicity dataset
- Apply influence functions (LiSSA approximation) to select valuable external data
- Experiment with different data selection strategies and fine-tuning methods

## Tech Stack

- **Python 3.x** - Core programming language
- **PyTorch** - Deep learning framework
- **Transformers (HuggingFace)** - Pre-trained model access and fine-tuning
- **Datasets** - Data loading and processing
- **Jupyter Notebook** - Interactive development environment
- **Pandas, NumPy** - Data manipulation
- **Scikit-learn** - Model evaluation metrics

## Repository Structure

```
molformer-finetuning-property-prediction/
├── notebooks/                              # Jupyter notebooks
│   ├── mlm_regression_training.ipynb       # MLM + regression fine-tuning
│   ├── influence_based_selection.ipynb     # Influence function data selection
│   └── exploration_finetuning_methods.ipynb # Alternative fine-tuning strategies
├── models/                                 # Trained models
│   ├── mlm_finetuned_molformer/           # Fine-tuned MolFormer model
│   ├── mlm_finetuned_tokenizer/           # Fine-tuned tokenizer
│   └── molformer_regression_model.pth     # Regression model weights
├── data/                                   # Dataset directory (gitignored)
│   └── .gitkeep
├── outputs/                                # Results and predictions
│   └── predictions.csv                     # Model predictions
├── archive/                                # Academic materials (archived)
│   ├── NNTI_Project_Report.pdf
│   └── report_assets/
├── requirements.txt                        # Python dependencies
├── LARGE_FILES.md                          # Download links for large model files
└── README.md                               # This file
```

## Setup / Installation

### Prerequisites
- Python 3.8 or higher
- CUDA-capable GPU (recommended for training, CPU will be slower)
- 8GB+ RAM
- ~5GB disk space for datasets and models

### 1. Clone the repository
```bash
git clone https://github.com/Raminyazdani/molformer-finetuning-property-prediction.git
cd molformer-finetuning-property-prediction
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

For CUDA support (recommended):
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

### 3. Download pre-trained models (optional)
Pre-trained models are available for download to skip the training steps. See [LARGE_FILES.md](LARGE_FILES.md) for download links.

Place downloaded files in:
- `models/mlm_finetuned_molformer/model.safetensors`
- `models/molformer_regression_model.pth`

**Note:** You can skip this step and train models from scratch using the notebooks.

## How to Run

### Starting Jupyter
Navigate to the repository root and start Jupyter Notebook:
```bash
jupyter notebook
```

**For Windows users:**
```powershell
jupyter notebook
```

### Notebooks Execution Order

Run the notebooks in the following sequence:

#### 1. MLM and Regression Fine-tuning
**Notebook:** `notebooks/mlm_regression_training.ipynb`

- Loads the Lipophilicity dataset from MoleculeNet
- Fine-tunes MolFormer using masked language modeling
- Trains a regression head for lipophilicity prediction
- Saves fine-tuned model and tokenizer to `models/`
- Generates predictions in `outputs/predictions.csv`

**Output:**
- `models/mlm_finetuned_molformer/` - Fine-tuned model
- `models/mlm_finetuned_tokenizer/` - Tokenizer
- `models/molformer_regression_model.pth` - Regression weights
- `outputs/predictions.csv` - Predictions

#### 2. Influence-Based Data Selection
**Notebook:** `notebooks/influence_based_selection.ipynb`

- Computes influence scores for external dataset samples
- Uses LiSSA approximation for efficient influence computation
- Selects high-impact samples based on influence scores
- Fine-tunes model with augmented training data
- Evaluates performance improvement

**Requirements:**
- External dataset: Place in `data/external_dataset.csv`
- Original dataset: Available via HuggingFace or place in `data/lipophilicity_dataset.csv`

**Output:**
- `outputs/gradients/` - Gradient computations
- Enhanced model performance metrics

#### 3. Exploration of Fine-tuning Methods
**Notebook:** `notebooks/exploration_finetuning_methods.ipynb`

- Explores alternative data selection strategies
- Compares different fine-tuning techniques
- Analyzes model performance across methods

## Data / Inputs

### Primary Dataset
- **Lipophilicity Dataset** from MoleculeNet benchmark
- Automatically downloaded via HuggingFace Datasets library
- Contains molecular SMILES strings and lipophilicity values
- Used for training and evaluation

### External Datasets (Optional)
For influence-based data selection experiments:
- Place external molecular datasets in `data/` directory
- Expected format: CSV with SMILES strings and property values
- See `notebooks/influence_based_selection.ipynb` for data requirements

### Pre-trained Model
- **MolFormer** from HuggingFace Model Hub
- Automatically downloaded on first run
- Chemical language model pre-trained on large molecular datasets

## Outputs

### Trained Models
- `models/mlm_finetuned_molformer/` - Fine-tuned MolFormer with MLM
- `models/mlm_finetuned_tokenizer/` - Corresponding tokenizer
- `models/molformer_regression_model.pth` - Regression model checkpoint

### Predictions
- `outputs/predictions.csv` - Molecular property predictions
- Contains SMILES strings and predicted lipophilicity values

### Metrics & Visualizations
Generated during notebook execution:
- Training/validation loss curves
- Performance metrics (R², MAE, RMSE)
- Influence score distributions
- Comparative analysis plots

## Reproducibility Notes

### Random Seeds
The notebooks set random seeds for reproducibility:
```python
torch.manual_seed(42)
np.random.seed(42)
```

### Environment
- Tested on PyTorch 2.0+, Transformers 4.30+
- GPU training recommended (CUDA 11.8+)
- CPU execution supported but significantly slower

### Data Splits
- Train/validation/test splits are deterministic
- Dataset loaded from HuggingFace with fixed splits

### Model Checkpoints
Pre-trained model weights are available for exact reproduction. See [LARGE_FILES.md](LARGE_FILES.md).

## Troubleshooting

### Import Errors
```bash
pip install torch transformers datasets pandas numpy scikit-learn jupyter
```

### CUDA/GPU Issues
- Ensure PyTorch is installed with CUDA support
- Check CUDA version compatibility: `torch.cuda.is_available()`
- For CPU-only: Models will still run but training will be slower

### Out of Memory
- Reduce batch size in notebook training loops
- Close other GPU-intensive applications
- Consider using gradient accumulation

### Model Download Failures
- Check internet connection
- Verify HuggingFace Hub accessibility
- Models may be automatically cached in `~/.cache/huggingface/`

### Missing External Datasets
- External datasets for influence-based selection are optional
- The main Lipophilicity dataset is downloaded automatically
- Check notebook documentation for external data format requirements

### Google Colab Compatibility
The notebooks were originally developed for Google Colab. The `drive.mount()` calls are commented out for local execution. To run in Colab:
1. Uncomment the `drive.mount()` calls in the first cell
2. Update paths as needed for your Colab environment

### Large Model Files
- Models can be trained from scratch (no download required)
- Training takes 1-2 hours on GPU, longer on CPU
- Download pre-trained weights from [LARGE_FILES.md](LARGE_FILES.md) to skip training

## Keywords

`molecular-property-prediction` `chemical-language-models` `molformer` `transfer-learning` `fine-tuning` `influence-functions` `cheminformatics` `deep-learning` `pytorch` `transformers` `lipophilicity-prediction` `smiles`

## License

This project is provided for educational and research purposes.

## References

- **MolFormer**: Ross et al. (2022) - Large-Scale Chemical Language Representations Capture Molecular Structure and Properties
- **MoleculeNet**: Wu et al. (2018) - MoleculeNet: A Benchmark for Molecular Machine Learning
- **Influence Functions**: Koh & Liang (2017) - Understanding Black-box Predictions via Influence Functions
- **LiSSA**: Agarwal et al. (2016) - Second-Order Stochastic Optimization for Machine Learning in Linear Time
