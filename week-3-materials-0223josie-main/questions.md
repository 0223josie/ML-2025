1. What are outliers, and how do you detect them? Outliers are unusual data points that deviate from the general pattern. It may be much larger or smaller than most values. It might not follow the trend or distribution of the rest of the dataset; or unrealistic. Outliers can arise from: Measurement errors (e.g., sensor glitches);Data entry mistakes; True rare events (e.g., fraud transactions, rare diseases). Outliers can be problematic because they may: Skew statistical measures (mean, variance); Mislead models (especially linear models); Sometimes, however, they contain valuable information (like fraud detection).

You can detect them using statistics (Z-score;If |z| > 3 (common rule), it’s considered an outlier., IQR-Compute Q1 (25th percentile) and Q3 (75th percentile).), visualization (boxplots-25%,50%,75%-, scatter plots-Help see unusual points in 2D.Histogram / Density plots: Highlight long tails.), or ML algorithms (Isolation Forest, LOF, One-Class SVM), depending on data complexity.

2. What sorts of techniques might you use to remove outliers? a. Z-score method: Remove points where |z| > 3 (or another threshold); b. Percentile / Clipping: Drop extreme values using cutoffs (e.g., remove top and bottom 1%); cap values at a maximum/minimum (a.k.a. **winsorizing**) c. Domain-Rule Filtering: Remove values that are impossible or unrealistic in context. d. Apply log, square root, or Box-Cox transformations to reduce impact of large values.e. Replace Instead of Remove -Replace outliers with: Mean/Median of the feature; Nearest Neighbor imputation (find similar points and replace).e. Use models less sensitive to outliers: Tree-based models (Random Forest, XGBoost),Robust regression (Huber, RANSAC).
winsorizing: Winsorizing is a statistical method to reduce the influence of extreme values (outliers) in a dataset by replacing them with less extreme values from the same dataset, rather than removing them. It involves capping the smallest and largest values in a distribution to specific percentiles, which makes the data and derived statistics like the mean more robust and accurate. This technique preserves the overall structure of the data while mitigating the distorting effect of outliers, making it useful in A/B testing and analyzing large or contaminated datasets.
3. Why do we scale data?
   Data scaling means transforming features so they are on a similar range or distribution (e.g., 0–1 or mean 0 and std 1). We do this because many machine learning algorithms are sensitive to the scale of input features. Scaling ensures features contribute more equally.In models like linear regression, logistic regression, neural networks, optimization is done via gradient descent.If features are on very different scales, the cost function contours are elongated → gradient descent takes longer zig-zag paths.With scaled data, the cost surface is smoother → convergence is faster and more stable.We scale data to ensure features are comparable, to make optimization faster, and to improve the performance of distance- and regularization-based models.
5. What techniques can we use to scale data?
   
| Technique                 | Best For                      | Sensitive to Outliers? |
| ------------------------- | ----------------------------- | ---------------------- |
| Standardization (Z-score): Centers data around mean = 0, std = 1.| Normal-like distributions     | Yes                    |
| Min-Max Scaling           | Neural nets, bounded inputs   | Yes                    |
| Robust Scaling            | Skewed data, outliers         | No                     |
| MaxAbs Scaling            | Sparse data (text, TF-IDF)    | Yes                    |
| Log / Power Transform     | Skewed data (income, counts)  | Reduces effect         |
| Unit Vector Norm          | Text, similarity-based models | Yes                    |
| Quantile Transform        | Highly skewed / irregular     | No                     |
In practice:Tree-based models (Random Forest, XGBoost) don’t need scaling, but for conceptualization, consider it anyway.
Standardization (Z-score scaling): Centers data around mean = 0, std = 1.Works well when features are roughly normally distributed.Common for linear regression, logistic regression, SVM, neural networks, PCA.
Min-Max Scaling (Normalization): Scales values to a fixed range (commonly [0, 1]).Sensitive to outliers.Useful for algorithms that require bounded input (e.g., neural networks with sigmoid/tanh activations).

Distance- and gradient-based models (SVM, kNN, k-means, logistic regression, neural nets) benefit a lot from scaling.

5. Name the three types of missing data.
MCAR → purely random, easiest to handle.
MAR → depends on observed data, manageable with statistical methods.
MNAR → depends on unobserved data, most problematic.

6. What is the difference between MNAR, MCAR, and MAR?
| Mechanism | Missingness Depends On              | Example                                 | Difficulty |
| --------- | ----------------------------------- | --------------------------------------- | ---------- |
| **MCAR**  | Neither observed nor missing values | Survey lost in mail                     | Easiest    |
| **MAR**   | Observed values only                | Older patients skip weight question     | Moderate   |
| **MNAR**  | Missing values themselves           | High-income people skip income question | Hardest    |

8. Name a few types of imputation methods and explain them
when data missing within 10-30%, mayhe mean is a good way. mean matters because 

 | Method            | Best For            | Pros                     | Cons                    |
| -------------------- | ------------------- | ------------------------ | ----------------------- |
| **Mean/Median/Mode**     | Small % missing     | Simple, fast             | Distorts variance       |
| Hot-Deck             | Survey data         | Realistic replacements   | Bias risk               |
| **KNN**                  | Tabular data        | Uses similarity          | Expensive               |
| Regression           | Correlated features | Leverages relationships  | Underestimates variance |
| Multiple Imputation  | MAR data            | Unbiased, robust         | Complex                 |
| Interpolation        | Time-series         | Natural for ordered data | Limited use             |
| Model-based (RF, EM) | Complex datasets    | Captures structure       | Heavy computation       |

8.What sorts of considerations should be made when deciding whether or not to impute data?
   a. Type of Missingness (MCAR, MAR, MNAR)**
   
9.  Suppose I have an imputation method that builds a model of the data and then uses that do fill missing values. First I apply the model to my dataset, and then I split it into test and train, and then I run and test my algorithm.  What is the problem?
this is a classic data leakage problem. what happened is You build an imputation model on the entire dataset (before splitting).That means the imputation model “sees” both training and test data. It learns patterns not just from training, but also from what will eventually become your test set.Then you split into train and test.Now, the test set isn’t truly independent. Information from the test set has already influenced the imputation model.Finally, you train and evaluate your predictive model.The test results will look better than they really are, because some knowledge of the test set “leaked” into training through imputation. This invalidates your estimate of generalization performance.

**correct way to do: You must treat imputation as part of your training pipeline**:**Split first → train/test**. Fit imputation model only on the training set.Apply that imputation model to transform both training and test sets.This way, the test set remains unseen during preprocessing.Then train your predictive model and evaluate on the (properly imputed) test set.**In practice, frameworks like scikit-learn Pipelines are designed exactly to prevent this kind of leakage.**

10. Why do we use a one hot encoder to encode categorical values?
   categorical values like "red", "blue", "green" can’t be directly processed. So we need to convert categories into numbers in a way that doesn’t mislead the model. **One-hot encoding creates a binary column for each category, marking presence with 1 and absence with 0.** **so the categories are still independent from each other.** a. it avoids false ordinal relationships If you label-encoded (Red=1, Blue=2, Green=3), models might assume Green > Blue > Red, which is meaningless. b.Works well with linear models. Regression, logistic regression, and SVMs treat each binary feature independently.Distance-based models
kNN, clustering, neural networks handle one-hot vectors well because categories are equidistant.
limitations: imitations of One-Hot Encoding High dimensionality: For features with thousands of categories (e.g., zip codes, words), one-hot creates huge sparse vectors.Not good for tree-based models (Random Forest, XGBoost) — they can handle label encoding directly without confusion.

11. What does the "sparse=False" flag do in sklearn's one-hot encoder?
The default is sparse = true, OneHotEncoder returns a **sparse matrix (SciPy csr_matrix)**. Why? Because one-hot encoded data is usually mostly zeros (only one 1 per row). Sparse matrices are memory-efficient: they only store the positions of nonzero values instead of all the zeros. Example: Instead of keeping [0, 0, 1, 0, 0], it just stores (row, col) = 2.
With **sparse=False: Forces the encoder to return a dense NumPy array instead of a sparse matrix**. Example: You get the full array [[0, 1, 0], [1, 0, 0]] instead of a sparse representation. Easier to inspect, print, and pass to models that don’t accept sparse input. but Uses more memory when you have lots of categories.
    
12. Name a few techniques for balancing imbalanced classes.
   In a classification problem, classes are said to be imbalanced when one class (or a few classes) has many more samples than the others. class imbalance is very common in machine learning (fraud detection, medical diagnosis, churn prediction, etc.).Problem: A naive model can achieve very high accuracy just by predicting the majority class every time. The minority class is often the one that matters most (fraud, disease, defects).Models trained on imbalanced data often have low recall for the minority. Misleading Metrics - Accuracy looks good, but precision, recall, and F1-score reveal poor performance.

**How to Handle Imbalanced Classes**Solution: Use resampling, class weighting, robust metrics, or specialized models.
Data-level methods: Oversample minority class (e.g., **SMOTE**). Undersample majority class. Data augmentation (images, text).
Algorithm-level methods: Use class weights (penalize mistakes on minority more).Use specialized algorithms (Balanced Random Forest, cost-sensitive learning).
Evaluation strategies: Use metrics like F1-score, Precision-Recall AUC, ROC-AUC, not just accuracy.
    
14. What techniques can we use to test the performance of an algorithm? you can do simple split, leave one out, cross-validation, 
15. What is "stratified" sampling? 
16. What is wrong with using accuracy as a metric for performance?
17. What is precision?  What is recall?
18. What is an F1-score?
19. What are ROC and AUC?

