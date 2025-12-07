Seurat Integration (CCA-based) is the most popular.  
Harmony is the recommended method. [A benchmark of batch-effect correction methods for single-cell RNA sequencing data](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-019-1850-9)  
Memory efficient, very fast compare with other methods so scales well to very large datasets, preserves global structure.   
Harmony is robust in the range of 20–50 PCs. Example with only 5 PC: Cell 1 = (1.2, -0.4, 0.8, 0.1, -0.6).
