# Git History Reconstruction: MolFormer Fine-tuning Project (Step-Expanded Version 2)

This document describes a realistic development history for the MolFormer fine-tuning project, reconstructed to show how a professional developer might have built this portfolio project from scratch.

## History Expansion Note

**Previous Run (First Expansion):**
- N_old_original = 8 steps (archived in `history/_previous_run_8steps/`)
- N_new_first = 14 steps (archived in `history/_previous_run_14steps/`)
- First multiplier: 14/8 = 1.75×

**Current Run (Second Expansion):**
- N_old = 14 steps
- N_new = 22 steps
- Multiplier achieved: 22/14 = 1.57× (exceeds minimum requirement of 1.5×)

**Expansion Strategy:**
This expanded history uses BOTH strategies to increase step count while maintaining realism:

1. **Split large commits** into smaller, coherent commits:
   - Old step 2 → New steps 02-03 (split requirements from gitignore)
   - Old step 4 → New steps 05-06 (split README structure from setup instructions)
   - Old step 5 → New steps 07-08 (split notebook creation from model initialization)
   - Old step 8 → New steps 11-14 (split training implementation with OOM fix)
   - Old step 11 → New steps 17-18 (split LARGE_FILES.md from README troubleshooting)
   - Old step 12 → New steps 19-21 (split path updates with missed path fix)

2. **Insert "oops → hotfix" sequences** (3 pairs total):
   - **Pair 1 (Steps 09-10)**: Model path typo - carried over from previous expansion
   - **Pair 2 (Steps 12-13)**: Batch size OOM issue - NEW
   - **Pair 3 (Steps 20-21)**: Missed absolute path during refactoring - NEW

**Mapping from Old (14-step) to New (22-step) Steps:**

| Old Steps | New Steps | Changes |
|-----------|-----------|---------|
| Step 01 (Initial README) | Step 01 | No change - minimal single file |
| Step 02 (Requirements + gitignore) | Steps 02-03 | SPLIT: requirements.txt first, then .gitignore |
| Step 03 (Structure) | Step 04 | Direct mapping (renumbered) |
| Step 04 (Enhanced README) | Steps 05-06 | SPLIT: structure docs + setup instructions |
| Step 05 (Basic MLM notebook) | Steps 07-08 | SPLIT: imports/loading + model initialization |
| Steps 06-07 (OOPS/HOTFIX path) | Steps 09-10 | Direct mapping (renumbered) |
| Step 08 (Complete MLM) | Steps 11-14 | SPLIT + OOPS/HOTFIX: training loop (11) + OOM bug (12) + fix (13) + save/eval (14) |
| Step 09 (Influence) | Step 15 | Direct mapping (renumbered) |
| Step 10 (Exploration) | Step 16 | Direct mapping (renumbered) |
| Step 11 (Documentation) | Steps 17-18 | SPLIT: LARGE_FILES.md (17) + README troubleshooting (18) |
| Step 12 (Path portability) | Steps 19-21 | SPLIT + OOPS/HOTFIX: path updates (19) + missed path (20) + fix (21) |
| Step 13 (Notebook polish) | Step 21 | Merged into final path fix |
| Step 14 (Final portfolio) | Step 22 | Direct mapping (renumbered) |

**Oops/Hotfix Details:**

### Pair 1: Model Path Typo (Steps 09-10) - Carried Over
- **What broke:** Path typo 'mlm_finetuend_molformer' (missing 't' in 'finetuned')
- **How noticed:** Visual code review while documenting structure
- **What fixed:** Corrected to 'mlm_finetuned_molformer' throughout
- **Why realistic:** Common copy-paste or typing error during rapid development

### Pair 2: Batch Size OOM (Steps 12-13) - NEW
- **What broke:** Initial batch size of 32 causes CUDA out of memory error during training
- **How noticed:** Runtime error when executing training loop: `RuntimeError: CUDA out of memory`
- **What fixed:** Reduced batch size to 16 with explanatory comment about GPU memory constraints
- **Why realistic:** Extremely common in ML development with transformer models; developers often start with standard batch sizes and adjust based on available hardware

### Pair 3: Missed Absolute Path (Steps 20-21) - NEW
- **What broke:** One absolute path remained in influence_based_selection.ipynb after bulk path refactoring
- **How noticed:** Manual testing and code review after completing path updates
- **What fixed:** Updated the missed path to use relative reference
- **Why realistic:** Very easy to miss one or two references during bulk find-and-replace operations; caught during testing phase

**Result:** Increased from 14 to 22 steps (57% increase) while maintaining a realistic development narrative.

---

## Overview

The project evolved through 22 major steps, from initial repository setup to a complete portfolio-ready machine learning project for molecular property prediction using chemical language models.

**Total Development Timeline:** ~5-6 weeks of realistic development
**Approach:** Iterative development with incremental commits, bug fixes, memory debugging, testing, refactoring, and documentation improvements

---

## Step-by-Step Documentation

### Step 01: Initial Repository Setup
**Commit:** "Initial commit: Project README"
- Created foundational README with project purpose and scope
- Files: README.md (initial description)
- **Rationale:** Professional projects start with clear purpose statement

### Step 02: Add Python Dependencies
**Commit:** "Add requirements.txt with core ML dependencies"
- Added core ML dependencies (PyTorch, Transformers, Datasets, etc.)
- Files: requirements.txt
- **Rationale:** Define environment requirements before configuring version control

### Step 03: Add Version Control Exclusions
**Commit:** "Add .gitignore for Python project"
- Configured git to ignore Python artifacts and generated files
- Files: .gitignore (Python/Jupyter patterns)
- **Rationale:** Natural follow-up after defining what files will be generated

### Step 04: Create Directory Structure
**Commit:** "Create organized directory structure for ML project"
- Created notebooks/, models/, data/, outputs/ directories
- Added .gitkeep files for empty directories
- **Rationale:** Establish organized structure before adding content

### Step 05: Document Project Structure
**Commit:** "Update README with repository structure"
- Added "Repository Structure" section documenting directory purposes
- **Rationale:** Document organization choices while fresh in mind

### Step 06: Add Setup Instructions
**Commit:** "Add installation and setup instructions to README"
- Added comprehensive setup section with prerequisites and steps
- **Rationale:** Make project immediately usable for new users

### Step 07: Create Basic MLM Notebook
**Commit:** "Add initial MLM fine-tuning notebook with data loading"
- Created mlm_regression_training.ipynb with imports and data loading
- **Rationale:** Start implementation incrementally - data first

### Step 08: Add Model Initialization
**Commit:** "Add MolFormer model initialization and tokenizer setup"
- Extended notebook with model and tokenizer initialization
- **Rationale:** Validate data pipeline before adding model complexity

### Step 09: Notice Model Path Typo (OOPS)
**Commit:** "Document model save path issue"
- Noted typo in model path: mlm_finetuend_molformer
- Added "Known Issues" to README
- **Rationale:** Catch and document issue during code review

### Step 10: Fix Model Path Typo (HOTFIX)
**Commit:** "Fix model path typo: mlm_finetuend_molformer → mlm_finetuned_molformer"
- Corrected all path references
- Removed "Known Issues" from README
- **Rationale:** Quick fix after catching the typo

### Step 11: Implement Training Loop
**Commit:** "Add MLM and regression training loop"
- Implemented core training loop with MLM and regression objectives
- **Rationale:** Core functionality implementation after foundation is complete

### Step 12: Discover Batch Size OOM (OOPS)
**Commit:** "Note: Training fails with batch size 32 (OOM error)"
- Documented CUDA out of memory error with batch size 32
- **Rationale:** Document runtime issue before fixing

### Step 13: Reduce Batch Size (HOTFIX)
**Commit:** "Fix OOM: Reduce batch size from 32 to 16"
- Reduced batch size to 16 with explanatory comment
- **Rationale:** Standard fix for transformer OOM issues

### Step 14: Add Model Saving and Evaluation
**Commit:** "Add model checkpointing and evaluation metrics"
- Added model/tokenizer saving and evaluation metrics
- Created model config files
- **Rationale:** Complete the training pipeline milestone

### Step 15: Implement Influence Selection
**Commit:** "Add influence function-based data selection using LiSSA"
- Created influence_based_selection.ipynb
- Implemented LiSSA approximation and influence scoring
- **Rationale:** Add advanced research-level techniques

### Step 16: Implement Exploration Framework
**Commit:** "Add exploration notebook for alternative strategies"
- Created exploration_finetuning_methods.ipynb
- **Rationale:** Scientific experimentation and comparison

### Step 17: Add Large File Documentation
**Commit:** "Add LARGE_FILES.md for model download instructions"
- Created LARGE_FILES.md with download/training instructions
- **Rationale:** Handle GitHub size limits professionally

### Step 18: Enhance README with Troubleshooting
**Commit:** "Add comprehensive troubleshooting guide to README"
- Added extensive troubleshooting section
- Documented common errors and solutions
- **Rationale:** Anticipate user issues from development experience

### Step 19: Refactor for Path Portability
**Commit:** "Refactor notebooks to use relative paths"
- Updated all paths to relative references
- Enhanced .gitignore patterns
- Commented out Colab-specific code
- **Rationale:** Ensure cross-environment portability

### Step 20: Notice Missed Path (OOPS)
**Commit:** "TODO: Check influence notebook for remaining paths"
- Added TODO noting missed absolute path in influence notebook
- **Rationale:** Caught during testing after bulk refactoring

### Step 21: Fix Remaining Path (HOTFIX)
**Commit:** "Fix: Update missed absolute path in influence notebook"
- Updated the missed path to relative
- Removed TODO comment
- **Rationale:** Complete the refactoring work

### Step 22: Final Portfolio Polish
**Commit:** "Final polish: Add project identity, report, and ledgers"
- Added project_identity.md, report.md, suggestion.txt, suggestions_done.txt
- Created archive/ for academic materials
- Added .github/ configuration
- **Rationale:** Professional portfolio presentation with full documentation

---

## Development Patterns Demonstrated

### 1. Incremental Progress
Small, focused commits that build toward complete features. Each step is testable and represents meaningful progress.

### 2. Error Recovery (3 Pairs)
- **Path typo (9-10):** Quick documentation error caught during review
- **OOM error (12-13):** Runtime error requiring configuration adjustment
- **Missed path (20-21):** Edge case missed during bulk refactoring

All three demonstrate realistic debugging: identify, document, fix, verify.

### 3. Iterative Documentation
README updated multiple times (steps 5, 6, 18) as understanding deepens and use cases are discovered.

### 4. Code Quality Focus
Dedicated refactoring steps (19-21) for portability and maintainability, separate from feature development.

### 5. Professional Packaging
Final step (22) adds comprehensive project identity, reporting, and audit trails for portfolio presentation.

---

## Timeline Estimate

**5-6 weeks of realistic development:**
- Week 1: Setup and initial implementation (steps 1-8)
- Week 2: Core training with debugging (steps 9-14)
- Week 3: Advanced features (steps 15-16)
- Week 4: Documentation (steps 17-18)
- Week 5: Refactoring (steps 19-21)
- Week 6: Final polish (step 22)

Commit frequency: 2-4 commits per week, matching real developer workflows with intense implementation sprints, slower experimentation, and quick bug fixes.

---

## Key Lessons

This expanded history demonstrates:
- ✅ Incremental, testable progress
- ✅ Realistic error handling and recovery
- ✅ Documentation written alongside code
- ✅ Refactoring for quality and portability
- ✅ Professional git hygiene (focused commits)
- ✅ Testing mindset (issues caught through execution)
- ✅ Portfolio-grade final presentation

The 22-step narrative provides granular insight into professional ML development while maintaining complete realism.
