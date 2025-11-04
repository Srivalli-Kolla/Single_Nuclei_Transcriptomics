# Single-Nuclei Transcriptomics Analysis Pipeline

This repository contains the R scripts used to process, integrate, cluster, annotate, and interpret single-nucleus RNA sequencing (snRNA-seq) data. The pipeline employs the **Seurat** ecosystem and follows best practices for quality control, batch correction , and differential gene expression (DGE) using the MAST test.

## 🚀 Pipeline Structure and Order

The analysis is structured into sequential scripts housed in logical directories for clarity and reproducibility.

| Step | Script | Directory | Analysis Stage |
| :--- | :--- | :--- | :--- |
| **1-2** | `01_qc_visualization.Rmd` / `02_filtering_normalization.Rmd` | `1.Preprocessing_QC` | **Initial QC & Normalization:** Strict filtering, SCTransform normalization, and data ready for integration. |
| **3** | `03_doublet_detection_scDblFinder.Rmd` | `2.Doublets_finding` | **Doublet Removal:** Identification and exclusion of doublet nuclei using scDblFinder. |
| **4** | `04_integration_clustering.Rmd` | `3.Annotation` | **Integration & Clustering:** Batch correction (Harmony/Seurat), UMAP, and identification of cell clusters. |
| **5** | `05_marker_gene_annotation.Rmd` | `3.Annotation` | **Preliminary Annotation:** Initial cell type assignment using canonical marker genes (DotPlots, FeaturePlots). |
| **6** | `06_deg_annotation.Rmd` | `3.Annotation` | **DGE & Final Annotation:** Cluster DGE (MAST), final standardized cell type labeling, and visualization. |
| **7** | `07_compositional_analysis_miloR.Rmd` | `4.Differential_Abundance` | **Cell Type Composition:** Differential abundance analysis (MiloR) across conditions. |
| **8** | `08_cell_cell_interactions_liana.Rmd` | `5.Cell_Cell_interactions` | **Cell-Cell Interactions:** Initial LIANA analysis on aggregated data alogng with factorization. |
