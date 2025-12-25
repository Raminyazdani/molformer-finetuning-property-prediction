# NNTI Deep Learning Project

**Project Type:** University Project  
**Primary Stack:** Python/Jupyter/PyTorch

## Description

This is a comprehensive deep learning project for the Neural Networks and Their Implementation (NNTI) course. The project involves fine-tuning a chemical language model (MolFormer) for molecular property prediction tasks. It includes three main tasks covering masked language modeling, regression, and additional analysis.

## Tech Stack

- Python 3.x
- PyTorch
- Transformers (HuggingFace)
- Jupyter Notebook
- NumPy
- Pandas
- Scikit-learn

## Folder Structure

```
Submission_13_-_7071538_Gopal_Mengi/
├── Task_1.ipynb                                      # Task 1: MLM fine-tuning
├── Task_2.ipynb                                      # Task 2: Regression task
├── Task_3.ipynb                                      # Task 3: Additional analysis
├── Task_1_mlm_finetuned_molformer_model/            # Fine-tuned MLM model
├── Task_1_mlm_finetuned_molformer_tokenizer/        # Fine-tuned tokenizer
├── Task_1_molformer_regression_model.pth            # Regression model weights
├── predictions.csv                                   # Model predictions output
├── NNTI_Project_Report.pdf                          # Project report
├── NNTI Project Report/                             # Report source files
└── README.md                                         # This file
```

## Setup / Installation

Install required dependencies:
```bash
pip install torch transformers datasets pandas numpy scikit-learn jupyter
```

For CUDA support (recommended):
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

Or using requirements file:
```bash
pip install -r requirements.txt
```

## How to Run

1. Navigate to the project directory:
```bash
cd Submission_13_-_7071538_Gopal_Mengi
```

2. Start Jupyter Notebook and run tasks in order:
```bash
jupyter notebook
```

**Run in sequence:**
- `Task_1.ipynb` - Fine-tune MolFormer with masked language modeling
- `Task_2.ipynb` - Regression task for molecular property prediction
- `Task_3.ipynb` - Additional analysis and evaluation

3. Each notebook loads the required pre-trained or fine-tuned models

## Inputs/Outputs

**Inputs:**
- Molecular datasets (SMILES strings)
- Lipophilicity dataset (for regression)
- Pre-trained MolFormer model (downloaded automatically)

**Outputs:**
- `Task_1_mlm_finetuned_molformer_model/` - Fine-tuned masked language model
- `Task_1_mlm_finetuned_molformer_tokenizer/` - Tokenizer for the fine-tuned model
- `Task_1_molformer_regression_model.pth` - Regression model checkpoint
- `predictions.csv` - Model predictions on test data
- Training logs and metrics
- Visualizations and analysis plots

## Notes

- This is a complete deep learning project with multiple tasks
- Pre-trained models are fine-tuned on specific datasets
- Uses HuggingFace Transformers library for chemical language models
- All paths are relative to the project directory
- Models are saved and can be loaded for inference
- GPU is recommended for training (CPU will be much slower)

## Troubleshooting

- If you get import errors: `pip install torch transformers datasets pandas numpy scikit-learn jupyter`
- For GPU/CUDA issues, ensure PyTorch is installed with CUDA support
- If out of memory, reduce batch size in the notebooks
- For Transformers issues, update: `pip install --upgrade transformers`
- If model downloads fail, check internet connection and HuggingFace Hub access
- Large models may require significant disk space (>2GB)
