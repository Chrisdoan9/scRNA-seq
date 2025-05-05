| Step                          | Seurat Function(s)                                             | Purpose                                                   |
|-------------------------------|----------------------------------------------------------------|------------------------------------------------------------|
| 1. Load Data                  | `Read10X()`, `CreateSeuratObject()`                            | Import raw matrix (from 10x, h5, or matrix)                |
| 2. Quality Control (QC)       | `subset()`, `PercentageFeatureSet()`                           | Filter out low-quality cells or empty droplets             |
| 3. Normalize Data             | `NormalizeData()`                                              | Adjust for sequencing depth across cells                   |
| 4. Find Variable Features     | `FindVariableFeatures()`                                       | Identify highly variable genes for downstream analysis     |
| 5. Scale Data                 | `ScaleData()`                                                  | Standardize expression values (mean=0, SD=1)               |
| 6. Dimensionality Reduction   | `RunPCA()`                                                     | Reduce noise and dimensionality using PCA                  |
| 7. Find Neighbors             | `FindNeighbors()`                                              | Construct graph of cell similarities                       |
| 8. Find Clusters              | `FindClusters()`                                               | Group similar cells using graph-based clustering           |
| 9. UMAP/t-SNE (Visualization) | `RunUMAP()` or `RunTSNE()`                                     | Visualize cell groups in 2D                                |
| 10. Cell Type Annotation      | `FeaturePlot()`, `VlnPlot()`, `DotPlot()` (manual); or `SingleR`, `Azimuth` (automated) | Assign biological labels to clusters |

