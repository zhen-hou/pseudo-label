# Covariate-Shift KRR Comparison Notes

This repository focuses on our new comparison experiments under covariate shift for kernel ridge regression.

## What We Compare

We compare multiple model-selection / reweighting strategies under source-target distribution shift, including:
- Source-only validation (naive baseline)
- Pseudo-label based validation
- Oracle target validation (reference)
- Importance-weighted and truncated importance-weighted variants

## Data Generation Used in Our Experiments

We use the project-aligned 1D setup:
- Feature space: `x in [0, 1]`
- True regression function: `f*(x) = cos(2*pi*x) - 1`
- Source covariate distribution:
  - `B/(B+1) * U[0, 1/2] + 1/(B+1) * U[1/2, 1]`
- Target covariate distribution:
  - `1/(B+1) * U[0, 1/2] + B/(B+1) * U[1/2, 1]`
- Labeled source response model: `y = f*(x) + noise`

## Files

- `KRR-CS-note-project-data.ipynb`
  - Main note notebook aligned with the above source/target data-generation process.
- `KRR-CS-compare-three-methods.ipynb`
  - Additional side-by-side comparison notebook.
- `myexample.ipynb`
  - Extra exploratory runs.
- `l2norm_imgs/`
  - Exported figures for covariate-shift fit comparison and L2-risk histograms.

## Quick Run

Open and run in order:
1. `KRR-CS-note-project-data.ipynb`
2. `KRR-CS-compare-three-methods.ipynb`

## License

MIT (see `LICENSE`).
