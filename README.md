# DA5401-A5-Manifold-Visualization
**Manifold Learning and Visualization on Yeast Gene Expression Data**  
**Name:** Sudha Sarraf  
**Roll Number:** ns25z247  


## 📂 Folder Structure
├── DA5401_A5_Manifold_Visualization.ipynb # Main Jupyter Notebook (all assignment parts)
├── yeast.arff # Dataset used (Yeast gene expression data)
├── DA5401_A5_Manifold_Visualization.pdf # Assignment PDF (for reference)
├── README.md # This file (submission guide)


---

## 🚀 How to Run

1. Place `yeast.arff` in the same directory as the notebook.  
2. Open `DA5401_A5_Manifold_Visualization.ipynb` in **Jupyter Notebook** or **JupyterLab**.  
3. Run all cells in order (`Kernel → Restart & Run All`).  
4. All required visualizations (t-SNE, Isomap, comparisons) and interpretations will be generated automatically.  

---

## 📑 Notebook Contents

### **Part A: Data Preprocessing and Feature Scaling**
- Load and parse the `yeast.arff` dataset using `scipy.io.arff`.  
- Explore feature dimensions and verify the total number of features (103).  
- Separate features and labels for analysis.  
- Scale features using **StandardScaler** to normalize magnitudes and improve algorithm convergence.  
- Create a **categorical index** by grouping the most frequent functional classes and multi-label combinations for visualization.

---

### **Part B: t-SNE and Veracity Inspection**
- Apply **t-SNE (t-Distributed Stochastic Neighbor Embedding)** to reduce the 103-dimensional data to 2D.  
- Experiment with **perplexity values = 5, 30, 50** and analyze how the visualization changes.  
- Select the optimal perplexity based on cluster separation and structure preservation.  
- Generate 2D scatter plots colored by category indices.  
- Perform **Veracity Inspection**:
  - **Noisy/Ambiguous Labels:** Points of one color embedded within another cluster.  
  - **Outliers:** Isolated points or distant clusters indicating rare or anomalous expression patterns.  
  - **Hard-to-Learn Samples:** Mixed-color regions showing overlapping functional categories.  
- Explain why such regions make classification more challenging.

---

### **Part C: Isomap and Manifold Learning**
- Implement **Isomap** to reduce the scaled feature matrix to 2D using geodesic (manifold) distances.  
- Experiment with neighborhood sizes (`n_neighbors = 5, 10, 15`) and visualize results.  
- Compare **Isomap vs. t-SNE**:
  - t-SNE preserves **local** structure (tight clusters).  
  - Isomap preserves **global** structure (overall manifold geometry).  
- Provide a side-by-side comparison plot of t-SNE and Isomap embeddings.  
- Discuss the **data manifold**, its curvature, and how manifold complexity influences the **difficulty of classification**.

---

### **📊 Key Visual Outputs**
- Scaled feature summary and shape verification.  
- t-SNE visualizations for multiple perplexity values (5, 30, 50).  
- Final t-SNE plot highlighting noisy labels, outliers, and mixed regions.  
- Isomap visualizations for multiple neighbor counts.  
- Side-by-side t-SNE vs. Isomap comparison figure.  
- Final Isomap plot with global structure interpretation.

---

## 🧠 Analytical Insights

- The Yeast dataset forms a **moderately curved manifold**, indicating continuous variation between gene functions.  
- **t-SNE** captures **local** neighborhood structure (fine-grained clusters).  
- **Isomap** captures **global** manifold relationships (overall geometry).  
- **t-SNE** is ideal for exploring **cluster purity and label noise**.  
- **Isomap** is ideal for understanding **large-scale relationships** between gene categories.  
- Classifiers struggle in regions of high curvature or overlapping colors, reflecting **biological ambiguity** and **intrinsic data complexity**.

---

## 📝 Notes for Evaluators

- The notebook is **self-contained**; only `yeast.arff` is required for execution.  
- All plots are labeled and accompanied by explanatory markdowns.  
- The analysis integrates both **visual interpretation** and **theoretical discussion**, aligning with the evaluation rubric.  
- Comparison plots clearly demonstrate the **difference between local and global structure preservation**.  
- Each section includes conclusions that connect **data visualization → manifold learning → classification insight**.

---

## ✅ Key Takeaways

- Real-world gene-expression data lies on **nonlinear manifolds** in high-dimensional space.  
- **t-SNE** effectively reveals **local clusters** but distorts global distances.  
- **Isomap** preserves **global geometry**, showing how functional groups relate across the dataset.  
- **Moderate manifold curvature** implies overlapping functional regions and increased classification difficulty.  
- Manifold learning provides a **powerful qualitative lens** for understanding biological datasets beyond simple metrics.

**Final Submission:**  
This notebook provides a complete end-to-end workflow for **manifold visualization and interpretation** of the Yeast gene-expression dataset, addressing all assignment questions with code, visualizations, and detailed theoretical explanations.
