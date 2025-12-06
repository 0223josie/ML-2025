# Lecture Topic Overview: Dimensionality Reduction

## Learning Objectives
Students will be able to:
- Understand the curse of dimensionality and its practical implications for machine learning algorithms
- Apply Principal Component Analysis (PCA) for feature extraction, data compression, and visualization
- Implement advanced dimensionality reduction techniques including Kernel PCA, Factor Analysis, t-SNE, and UMAP
- Choose appropriate dimensionality reduction methods based on data characteristics and analysis goals
- Interpret principal components, factor loadings, and their relationship to original features
- Evaluate dimensionality reduction quality using variance explained, scree plots, and visualization techniques
- Understand the mathematical foundations of eigenvalue decomposition and manifold learning
- Apply dimensionality reduction in machine learning pipelines for improved performance and visualization

## Topics Covered
**Curse of Dimensionality:**
- Hughes Phenomenon and the relationship between features and model performance
- Distance behavior in high-dimensional spaces (concentration effects)
- Impact on different algorithms (KNN particularly susceptible)
- Experimental demonstration with random data across increasing dimensions

**Principal Component Analysis (PCA):**
- Mathematical foundation: eigenvalue/eigenvector decomposition of covariance matrices
- Step-by-step PCA algorithm implementation
- Variance explained and component selection using scree plots and cumulative variance
- Data reconstruction and compression applications
- Practical implementation with MNIST handwritten digits dataset

**Advanced PCA Extensions:**
- **Kernel PCA**: Non-linear dimensionality reduction using kernel trick
- Polynomial, RBF (Gaussian), and sigmoid kernel functions
- Comparison with standard PCA on non-linear data (concentric circles)

**Factor Analysis:**
- Distinction from PCA: latent variable modeling vs. variance maximization
- Factor extraction methods: Principal Axis Factoring (PAF), Maximum Likelihood, Least Squares
- Factor rotation: Orthogonal (Varimax) vs. Oblique (Promax) methods
- Interpretation: factor loadings, communalities, and unique variances
- Suitability assessment: Kaiser-Meyer-Olkin (KMO) test and Bartlett's sphericity test
- Factor selection: Kaiser criterion, scree plots, and parallel analysis

**Adaptive/Manifold Learning Techniques:**
- **t-SNE (t-Distributed Stochastic Neighbor Embedding)**:
  - Probability distribution approach for similarity preservation
  - Kullback-Leibler divergence minimization
  - Local structure preservation strengths and global structure limitations
  - Computational considerations and parameter sensitivity (perplexity)
  
- **UMAP (Uniform Manifold Approximation and Projection)**:
  - Mathematical foundations in Riemannian geometry and algebraic topology
  - Graph-based approach with k-NN graph construction
  - Balanced global and local structure preservation
  - Parameter control: n_neighbors (global/local balance) and min_dist (embedding fuzziness)
  - Computational efficiency advantages over t-SNE

## Practical Skills
After completing this section, students can:
- Diagnose high-dimensional data problems and select appropriate reduction techniques
- Implement PCA with proper component selection using explained variance criteria
- Apply Kernel PCA for non-linear data patterns
- Conduct Factor Analysis with proper rotation and interpretation
- Use t-SNE and UMAP for effective data visualization
- Evaluate dimensionality reduction quality through multiple metrics
- Integrate reduction techniques into machine learning workflows
- Handle large datasets efficiently using scalable reduction methods

## Prerequisites
- Linear algebra: matrix operations, eigenvalues, eigenvectors
- Basic statistics: variance, covariance, correlation
- Understanding of distance metrics and similarity measures
- Lectures 01-03: Python ecosystem, data preprocessing, and scikit-learn pipelines

## Key Materials
**Core Notebook:**
- `1-dimensionality-reduction.ipynb`: Comprehensive treatment covering:
  - Curse of dimensionality experiments and demonstrations
  - Complete PCA implementation with MNIST dataset examples
  - Kernel PCA applications to non-linear data
  - Factor Analysis workflow including rotation and interpretation
  - t-SNE and UMAP comparisons with Swiss Roll and mammoth datasets
  - Practical exercises with real-world high-dimensional data

**Supporting Materials:**
- `assets/hughes_phenomenon.png`: Visualization of feature-performance relationship
- `assets/mammoth_md.gif`: UMAP min_dist parameter animation
- `assets/mammoth_nn.gif`: UMAP n_neighbors parameter animation
- Data files for hands-on exercises (mammoth 3D scan data)

## Time Estimate
- Curse of dimensionality concepts: 1-2 hours
- PCA theory and implementation: 4-5 hours
- Kernel PCA and Factor Analysis: 3-4 hours
- t-SNE and UMAP: 3-4 hours
- Practical exercises and comparisons: 2-3 hours
- **Total: 13-18 hours**

## Assessment Preparation
This section prepares students for:
- Choosing appropriate dimensionality reduction for different data types
- Implementing reduction techniques in preprocessing pipelines
- Interpreting reduced-dimension results and explaining components
- Balancing computational efficiency with information preservation
- Visualizing high-dimensional data effectively for exploratory analysis