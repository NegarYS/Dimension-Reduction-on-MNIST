## 🧮  Dimension Reduction on MNIST

### 📖 Introduction
High-dimensional datasets such as **MNIST** (28×28 grayscale images of handwritten digits) present challenges for visualization and analysis.  
This project applies **dimension reduction** techniques to project MNIST into **2D space** for visualization and evaluation. Two approaches are compared:

1. **Principal Component Analysis (PCA)** – a linear method preserving global variance.  
2. **t-distributed Stochastic Neighbor Embedding (t-SNE)** – a nonlinear method that focuses on preserving local neighborhoods.  

The analysis aims to evaluate the **effectiveness of each method** and the impact of **perplexity** on t-SNE embeddings.

---

### ⚙️ Implementation
- **Dataset**: MNIST (70,000 images), with a **subset of 40,000 samples** for computational efficiency.  
- **Preprocessing**:
  - Flattened images into 784-dimensional vectors.  
  - Normalization applied for consistency.  
- **Dimension Reduction Techniques**:
  1. **PCA** with 2 components.  
  2. **t-SNE** with different **perplexity values**: 5, 10, 30, 50, 100, 130.  
- **Evaluation Metrics**:
  - **Trustworthiness** – measures preservation of local structures.  
  - **KL Divergence** – measures embedding quality for t-SNE.  
- **Visualization**: Embeddings were plotted in 2D with digit labels.

---

### 📊 Results
1. **PCA**:
   - Computed in only a few seconds.  
   - Provided a rough global structure of the digits.  
   - Trustworthiness ≈ **0.78** (relatively low).  

2. **t-SNE (Perplexity = 30)**:
   - Produced clear separation between digit clusters.  
   - Trustworthiness ≈ **0.95**, significantly higher than PCA.  
   - KL Divergence was relatively small, indicating high embedding quality.  

3. **Perplexity Study**:
   - Low perplexity (5, 10) resulted in scattered clusters and lower trustworthiness.  
   - Medium perplexity (30–50) produced the most meaningful and stable clusters.  
   - Very high perplexity (100–130) reduced the clarity of clusters and increased runtime.  
   - **Optimal perplexity ≈ 30–50**.  

4. **Runtime Comparison**:
   - PCA: < 5 seconds.  
   - t-SNE: Several minutes, depending on perplexity.  

---

### 🎯 Conclusion
- **PCA** is suitable for **quick global analysis**, but not for fine-grained structure preservation.  
- **t-SNE** excels at **local neighborhood preservation** and is therefore more appropriate for **visualizing handwritten digit clusters**.  
- **Perplexity** is a critical hyperparameter: too low or too high harms performance, while values around **30–50** provide the best trade-off.  
- The project demonstrates how **dimension reduction techniques** can provide insights into high-dimensional data such as MNIST, with t-SNE offering superior visualization at a higher computational cost.
