# Portfolio Readiness Report

## Phase 0 - Initial Self-Setup

### 0.1 Created Required Files
- Created report.md (this file)
- Created suggestion.txt with comprehensive audit findings
- Created suggestions_done.txt (ledger for applied changes)
- Created project_identity.md with professional identity

### 0.2 Copilot Guidance Files
- `.github/copilot-instructions.md` already exists
- No additional guidance files needed at this time

---

## Phase 1 - Project Understanding

### 1.1 Repository Initial State
- Repository path: `/home/runner/work/molformer-finetuning-property-prediction/molformer-finetuning-property-prediction`
- Primary stack: Python, PyTorch, Transformers (HuggingFace), Jupyter Notebooks
- Domain: Chemical language models, molecular property prediction (lipophilicity)
- Current structure shows clear academic/course work traces (NNTI, Task_1/2/3, submission naming)

### 1.2 Project Understanding Summary
This project demonstrates fine-tuning of MolFormer (a pre-trained chemical language model) for molecular property prediction. It consists of three main components:

1. **MLM + Regression Training** (Task_1.ipynb): Fine-tunes MolFormer using masked language modeling and regression on the Lipophilicity dataset from MoleculeNet
2. **Influence-Based Data Selection** (Task_2.ipynb): Uses influence functions (LiSSA approximation) to select high-impact samples from external datasets
3. **Exploration of Fine-tuning Methods** (Task_3.ipynb): Experiments with alternative data selection strategies and fine-tuning techniques

**Key Technologies:**
- MolFormer pre-trained model (from HuggingFace)
- SMILES molecular representations
- Lipophilicity prediction (drug discovery metric)
- Influence functions for data selection
- Transfer learning and fine-tuning

### 1.3 Professional Identity Defined
Created comprehensive project_identity.md with:
- Display Title: "MolFormer Fine-tuning for Molecular Property Prediction"
- Repo Slug: molformer-finetuning-property-prediction (matches current repo name)
- Tagline focused on chemical language models and transfer learning
- 12 relevant topics/keywords for discoverability
- Clear problem statement and approach description
- Documented inputs (SMILES, datasets, pre-trained models) and outputs (fine-tuned models, predictions, metrics)

### 1.4 Naming Alignment Plan
Based on audit findings in suggestion.txt, the following changes are planned:

**File/Folder Renames (Safe, Reference-Updated):**
1. Task_1.ipynb → notebooks/mlm_regression_training.ipynb
2. Task_2.ipynb → notebooks/influence_based_selection.ipynb
3. Task_3.ipynb → notebooks/exploration_finetuning_methods.ipynb
4. Task_1_mlm_finetuned_molformer_model/ → models/mlm_finetuned_molformer/
5. Task_1_mlm_finetuned_molformer_tokenizer/ → models/mlm_finetuned_tokenizer/
6. predictions.csv → outputs/predictions.csv
7. NNTI_Project_Report.pdf → archive/NNTI_Project_Report.pdf
8. NNTI Project Report/ → archive/report_assets/

**Structure Changes:**
- Create notebooks/, models/, data/, outputs/, archive/ directories
- Move existing files into appropriate directories
- Update .gitignore to include common Python patterns

**Absolute Path Elimination:**
- Replace all /content/drive/MyDrive/... paths with relative ./models/, ./data/, ./outputs/ paths
- Handle drive.mount() calls (comment out with explanation for local execution)
- Document data requirements in README for external datasets

**README Complete Rewrite:**
- Remove all academic/course language (NNTI, University Project, Task 1/2/3, assignment language)
- Align with project_identity.md
- Add portfolio-grade structure with clear setup, usage, data instructions, outputs, troubleshooting

**Notebook Content Updates:**
- Update cell titles from "Task 1/2/3" to descriptive professional titles
- Remove assignment instruction language
- Update all internal references to new file paths

---

## Phase 2 - Pre-Change Audit Results

### 2.1 Summary of Findings
Completed comprehensive scan and documented 35 issues in suggestion.txt:
- 8 file/folder renames needed (Task_ prefixes, NNTI references)
- 15 absolute path issues (Google Drive, Colab-specific paths)
- 12 academic/assignment traces (course names, task language, assignment instructions)
- Complete README rewrite required
- Structure reorganization needed
- .gitignore expansion needed

### 2.2 Critical Path Issues
The most critical issues blocking portability:
1. Absolute Google Drive paths in all notebooks - prevents local execution
2. drive.mount() calls - Colab-specific, breaks local Jupyter
3. No data/ directory or instructions for obtaining external datasets
4. Flat project structure with no clear organization

### 2.3 Academic Traces Identified
- "NNTI" (Neural Networks and Their Implementation) course identifier
- "University of Saarland" references
- "Submission_13_-_7071538_Gopal_Mengi" old folder name
- "Task 1/2/3" throughout notebooks and README
- "Your task is to complete..." assignment language
- Academic report PDF and assets

All findings documented in suggestion.txt with STATUS=NOT_APPLIED. Changes will be applied in Phase 3.

---

## Phase 3 - Portfolio-Readiness Changes

### Next Steps
- Apply changes systematically
- Update suggestion.txt STATUS to APPLIED
- Log all changes in suggestions_done.txt
- Verify runability after changes

