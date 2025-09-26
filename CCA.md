CCA (Canonical Correlation Analysis) is one of Seurat’s batch correction methods, especially in earlier versions (like Seurat v2 and early v3).  
	•	X = gene matrix from dataset A (cells × genes)  
	•	Y = gene matrix from dataset B  
CCA finds:  
	•	A linear combination of genes in X:  
→ u = a₁·X₁ + a₂·X₂ + ... + aₙ·Xₙ  
	•	A linear combination of genes in Y:  
→ v = b₁·Y₁ + b₂·Y₂ + ... + bₘ·Yₘ  

Such that:  

The correlation between u and v is as high as possible.  

These u and v are called canonical variables — the most “aligned” versions of each dataset.
