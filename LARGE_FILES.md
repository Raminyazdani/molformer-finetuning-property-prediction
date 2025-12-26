# Large Model Files

These files are intentionally not stored in GitHub (to avoid GitHub's size limits).
They are available for download from Google Drive.

## Download Links

| Path | Size (MB) | Google Drive Link |
|---|---:|---|
| `models/mlm_finetuned_molformer/model.safetensors` | 178.57 | https://drive.google.com/open?id=1_tC1H5PFQw3_4DUSbzXrWhV1S21V30Q4 |
| `models/molformer_regression_model.pth` | 171.81 | https://drive.google.com/open?id=1zTr4j-8hS65is45U82C9s77cuowSRMkR |

## Installation

1. Download the files from the links above
2. Place them in the specified paths:
   - `models/mlm_finetuned_molformer/model.safetensors`
   - `models/molformer_regression_model.pth`
3. Ensure the `models/` directory structure matches the paths above

## Note

The project can run without these pre-trained files by training models from scratch using the notebooks. However, downloading these files allows you to skip the time-intensive training steps and directly use the fine-tuned models for inference.
