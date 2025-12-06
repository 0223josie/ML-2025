# Lecture Topic Overview: Fundamental Classification and Regression Algorithms

## Learning Objectives
Students will be able to:
- Understand and implement linear regression with proper assumptions and diagnostics
- Apply logistic regression for binary and multiclass classification problems
- Implement k-Nearest Neighbors (k-NN) for both classification and regression tasks
- Evaluate classification models using comprehensive metrics beyond accuracy
- Understand the mathematical foundations of linear models and distance-based methods
- Handle categorical and numerical features appropriately for different algorithms
- Compare algorithm performance and select appropriate methods based on problem characteristics

## Topics Covered
**Linear Regression Fundamentals:**
- Simple and multiple linear regression formulation
- Ordinary Least Squares (OLS) estimation and assumptions
- Coefficient interpretation and statistical significance
- Residual analysis and model diagnostics
- Handling categorical predictors and interaction terms
- Assumptions: linearity, independence, homoscedasticity, normality

**Logistic Regression:**
- Binary classification using logistic function and odds ratios
- Maximum likelihood estimation for parameter learning
- Sigmoid function and probability interpretation
- Multiclass extensions: one-vs-rest and multinomial approaches
- Feature scaling importance and coefficient interpretation
- Comparison with linear regression: continuous vs. categorical outcomes

**k-Nearest Neighbors (k-NN):**
- Distance-based classification and regression
- Choice of k parameter and its impact on bias-variance trade-off
- Distance metrics: Euclidean, Manhattan, Minkowski, and custom distances
- Curse of dimensionality effects on k-NN performance
- Computational considerations and scalability challenges
- Local vs. global decision boundaries

**Classification Evaluation Metrics:**
- Confusion matrix construction and interpretation
- Accuracy limitations and when to use alternative metrics
- Precision, recall, and F1-score for imbalanced datasets
- ROC curves and AUC analysis for threshold selection
- Precision-recall curves for highly imbalanced data
- Multiclass evaluation: macro and micro averaging

**Probability Theory Applications:**
- Bayes' theorem and its relevance to classification
- Joint probability distributions and conditional independence
- Maximum likelihood estimation principles
- Probability calibration and reliability diagrams

## Practical Skills
After completing this section, students can:
- Implement linear regression with proper diagnostic checking
- Build logistic regression models for binary and multiclass problems
- Apply k-NN with appropriate distance metrics and parameter tuning
- Evaluate classification models using multiple complementary metrics
- Create and interpret ROC curves and precision-recall curves
- Handle mixed data types (categorical/numerical) appropriately
- Select appropriate algorithms based on data characteristics and problem requirements

## Prerequisites
- Basic statistics: correlation, hypothesis testing, probability distributions
- Linear algebra: matrix operations, vector spaces
- Calculus: derivatives for understanding optimization (helpful)
- Lectures 01-03: Data preprocessing, feature encoding, and evaluation methods

## Key Materials
**Core Notebooks:**
- `0-linear-regression.ipynb`: Complete linear regression implementation with assumptions testing and diagnostics
- `1-logistic_regression.ipynb`: Binary and multiclass logistic regression with probability interpretation
- `2-knn-classifiers.ipynb`: k-NN implementation with distance metrics and parameter optimization
- `3-evaluating-classifiers.ipynb`: Comprehensive classification evaluation using multiple metrics and visualization

**Supporting Materials:**
- `assets/joint_probability_diagram.webp`: Visual aid for probability theory concepts
- `assets/probability_theory1.png`: Bayes' theorem and conditional probability illustrations
- `data/federalistpapers.csv`: Historical text classification dataset for practical exercises
- `old/`: Additional materials showing alternative implementations and extended examples

## Time Estimate
- Linear regression theory and implementation: 3-4 hours
- Logistic regression and probability concepts: 3-4 hours
- k-NN algorithms and distance metrics: 2-3 hours
- Classification evaluation and metrics: 3-4 hours
- **Total: 11-15 hours**

## Assessment Preparation
This section prepares students for:
- Fundamental algorithm implementation in programming assignments
- Model evaluation and comparison in project work
- Understanding trade-offs between simple and complex models
- Proper use of evaluation metrics for different problem types
- Building foundation for ensemble methods and advanced algorithms