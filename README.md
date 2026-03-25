### Cell Type Annotation in Transcriptionally Homogeneous Single-Cell Data
#### An Evaluation of Differential Expression Analysis and Advanced Embedding Methods

This repo contains the code used for the Master's thesis "Cell Type Annotation in Transcriptionally Homogeneous Single-Cell Data: An Evaluation of Differential Expression Analysis and Advanced Embedding Methods" by Anton Wang and Gustav Helms (2025). The Thesis was supervised by Ole Winther (University of Copenhagen) and Alexander Valentin (Novo Nordisk). 
\\
Below is an overview of the structure of the repository and the contents of each folder. Within the two code folders, there are OVERVIEW files that provide detailed instructions on how to run the code and reproduce the analyses presented in the thesis.

#### Overview of the Repository
- 'part_1': Contains code and analysis for the evaluation of how transcriptanly homogenous samples inflfluence the performance of cell type annotation methods. 
- 'part_2': Contains code for the analysis of advanced embedding methods for cell type representation and annotation. 
- 'presentations/': Contains presentation figures and code for creating them. 
- 'PAPER.pdf': Contains the final thesis report.
- 'SLIDES.pdf': Contains the slides for the final presentation of the thesis.

![Alt text](presentations/ag_speciale_frontpage.png)


##### Abstract

Single-cell RNA sequencing (scRNA-seq) has become an integrated part of quality control in stem cell research, but standard differential expression (DE) analysis may fail to distinguish closely related cell types in transcriptionally homogeneous samples. This thesis addresses two questions: (1) How does transcriptional homogeneity affect DE-based cell type identification? (2) Can alternative embedding methods improve discrimination in homogeneous settings? In Part 1 of this thesis, we examine the effect of increasing transcriptional homogeneity on differential expression analysis. By subsetting a large cell atlas into smaller groups of varying homogeneity based on
average Pearson correlation between cell types, we confirmed that DE analysis performance degrades substantially in homogeneous samples. These findings motivated Part 2, where we investigate whether alternative embedding methods can improve cell type discrimination in such challenging settings. In Part 2, we compared four data representations: highly variable genes (HVG) from log-normalized counts, principal component analysis (PCA) embeddings, variational autoencoder (VAE) latent embeddings, and VAE embeddings refined by latent diffusion model (LDM) denoising. Performance was evaluated using cell-type Local Inverse Simpson Index (cLISI) scores and label transfer accuracy via multinomial logistic regression. Contrary to expectations, PCA consistently performed similar or better than the more complex methods, with LDM providing minimal to no improvement over VAE, across both homogeneous and heterogeneous settings. These results suggest that improved representation learning alone is insufficient to overcome limitations in cell type discrimination, highlighting the role of annotation practices, evaluation frameworks and the lack of biological context in current modeling framework.


