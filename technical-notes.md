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

Common mistakes in single-cell analysis.

Group all the cells from each condition together, then do differential gene expression (DGE) at the individual cell level.

Example:  
	•	You have 5 healthy samples and 5 disease samples.  
	•	Each sample has thousands of cells.  
	•	Instead of treating the samples separately, the researcher:  
	•	Takes all healthy cells together, and  
	•	Takes all disease cells together, and  
	•	Compares gene expression cell by cell, like there’s 20,000 “healthy” cells vs 20,000 “disease” cells.

R1 Barcodes and UMI tells you which cell and which molecule the read came from  
R2 cDNA (the actual gene sequence) tells you what gene was expressed  
I1 is the 8 bp sample barcode  

R1 [Cell Barcode][UMI][Spacer]

```
@A00489:28:HHWY3DSX2:1:1101:1000:1000 1:N:0:ATTACTCG
AAACCTGAGAAACCATTTGCATCGT
+
FFFFFFFFFFFFFFFFFFFFFFFFF
```
• First 16 bases: Cell barcode (e.g., AAACCTGAGAAACCAT)  
• Next 10 bases: UMI (e.g., TTGCATCGT)  
• Combined = 26 bp for R1

Barcode inclusion list (formerly barcode whitelist), cell barcode, 16 bases.

