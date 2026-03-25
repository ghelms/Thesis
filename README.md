# Cell Type Annotation in Transcriptionally Homogeneous Single-Cell Data
## An Evaluation of Differential Expression Analysis and Advanced Embedding Methods

This repository contains the code used for the Master's thesis:
Cell Type Annotation in Transcriptionally Homogeneous Single-Cell Data: An Evaluation of Differential Expression Analysis and Advanced Embedding Methods (2025), by Anton Wang and Gustav Helms.

Supervisors:
- Ole Winther (University of Copenhagen)
- Alexander Valentin (Novo Nordisk)

## Repository Overview

- [part_1](part_1): Differential-expression-based analysis of cell type annotation under varying transcriptional homogeneity.
- [part_2](part_2): Representation learning analysis using HVG/PCA/VAE/VAE+diffusion embeddings.
- [presentations](presentations): Figures, slide assets, and presentation-related plotting code.
- PAPER.pdf: Final thesis report.
- SLIDES.pdf: Final thesis presentation.

![Front page image](presentations/ag_speciale_frontpage.png)

## Scientific Scope

The thesis addresses two main questions:

1. How does transcriptional homogeneity influence differential-expression-based cell type identification?
2. Can advanced learned embeddings improve discrimination in homogeneous settings?

## Part 1 Summary

Part 1 builds groups of tissue-celltype combinations spanning increasing similarity/diversity and evaluates how this affects marker-based annotation.

Main workflow:
1. Sample or construct group definitions with controlled similarity levels.
2. Run differential expression per condition and iteration.
3. Run scEnrichment (CELLiD) on marker lists.
4. Evaluate top-k matching and rank-based metrics.

Key files:
- [part_1/overview.txt](part_1/overview.txt)
- [part_1/analysis/DE_one_disco.Rmd](part_1/DE_one_disco.Rmd)
- [part_1/analysis/DE_two_to_eight_disco.rmd](part_1/DE_two_to_eight_disco.rmd)
- [part_1/analysis/scEnrichment.rmd](part_1/scEnrichment.rmd)
- [part_1/CELL_TYPE_SUBSETS/Sampling.rmd](part_1/CELL_TYPE_SUBSETS/Sampling.rmd)

## Part 2 Summary

Part 2 benchmarks multiple representations for downstream cell type annotation quality:
- HVG (log-normalized feature baseline)
- PCA embeddings
- VAE latent embeddings
- Diffusion-denoised VAE latents

Main workflow:
1. Split data into train/validation/test.
2. Train VAE and extract latent spaces.
3. Train diffusion denoiser in latent space.
4. Generate denoised embeddings for multiple denoising step counts.
5. Evaluate cLISI and label transfer performance.
6. Aggregate and visualize grid-search and evaluation outputs.

Key files:
- [part_2/OVERVIEW.txt](part_2/OVERVIEW.txt)
- [part_2/src/pipeline.py](part_2/src/pipeline.py)
- [part_2/experiments/run_grid_search.py](part_2/experiments/run_grid_search.py)
- [part_2/experiments/evaluate_label_tranfer.py](part_2/experiments/evaluate_label_tranfer.py)
- [part_2/experiments/plot_results.py](part_2/experiments/plot_results.py)
- [part_2/experiments/plot_label_transfer.py](part_2/experiments/plot_label_transfer.py)

## Expected Outputs

Part 1 produces:
- Differential expression marker logs.
- scEnrichment logs.
- Aggregated prediction/evaluation tables and plots.

Part 2 produces:
- Grid-search result tables.
- Consolidated train/validation/test AnnData files with embeddings.
- Label transfer evaluation tables.
- Plot artifacts for cLISI and label transfer comparisons.
- Cached model checkpoints and latent arrays.

## Notes

- The project includes some legacy and intermediate analysis files from iterative development.
- The most practical entry points are the OVERVIEW files in each part folder and the experiment scripts in [part_2/experiments](part_2/experiments).
