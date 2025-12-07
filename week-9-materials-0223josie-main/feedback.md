# Assignment Feedback: Week 9: Classification Part2

**Student:** 0223josie
**Raw Score:** 26/27 (96.3%)
**Course Points Earned:** 4

---

## Problem Breakdown

### **Exercise 1** (8/9 = 88.9%)

**Part ex1-part2** (ex1-part2.answer): 2/2 points

_Feedback:_ Clear explanation of why scaling matters, referencing ranges, mean/std, and impact on the SVM decision boundary. Ties well to the pipeline used. Minor note: avoid leaving placeholder text in the cell. Otherwise, solid understanding.

**Part ex1-part3** (ex1-part3.fill): 1/1 points

_Feedback:_ Good job replacing the TODO with functional code. You implemented a pipeline with scaling, iterated over C and gamma, computed F1/accuracy, tracked the best model, and printed results. Note: you’re evaluating on training data; consider a split or CV next time.

**Part ex1-part4** (ex1-part4.answer): 2/2 points

_Feedback:_ Clear explanation of C and gamma effects and a justified best setting with metrics. Reasoning about under/overfitting is sound. Note: the “localized influence” description of gamma is more RBF-centric; for poly it scales feature interactions. Overall solid.

**Part ex1-part5** (ex1-part5.code): 1/1 points

_Feedback:_ You clearly explained the roles of C and gamma, identified a best setting (C=0.001, gamma=10) based on your results, and discussed the effect of added noise. Good linkage to your prior experiments. Nice job.

**Part ex1-part6** (ex1-part6.answer): 1/1 points

_Feedback:_ Good job: you used an RBF kernel with gamma=0.1 and C=0.001, evaluated via cross-validation, and compared against your best poly model. Your summary is clear and aligned with your workflow. If possible, cite the exact CV means/std from your output for precision.

**Part ex1-part7** (ex1-part7.fill): 1/1 points

_Feedback:_ Good job replacing the TODO with functional code. You built an RBF grid search with scaling, computed F1/accuracy, added CV accuracy, tracked the best model, and produced clear visualizations and comparisons. Consider selecting best by CV metrics rather than train F1.

**Part ex1-part8** (ex1-part8.answer): 0/1 points

_Feedback:_ Your explanation contradicts your prior results. You reported RBF ~88% CV/F1 and best poly ~89%, but here you claim a 9.1% F1 gap favoring RBF and slight overfitting. Please base your discussion on your computed CV/train metrics and plots; as shown, poly slightly edged RBF.

---

### **Exercise 2** (8/8 = 100.0%)

**Part ex2-part2** (ex2-part2.code): 3/3 points

_Feedback:_ Good job: you loaded/split data previously, encoded authors with LabelEncoder, and applied StandardScaler via pipelines. This satisfies the scaling requirement for modeling. For later disputed predictions, ensure you apply the same scaler to X_test as well.

**Part ex2-part3** (ex2-part3.code): 3/3 points

_Feedback:_ Full credit. You correctly built SVC and KNN and already computed 5-fold mean CV accuracy in prior work. This cell fits on train and predicts test (fine but not needed for this step). For Step 2, ensure you report the mean CV accuracies as you did earlier.

**Part ex2-part4** (ex2-part4.answer): 2/2 points

_Feedback:_ Good job: you trained both models, generated predictions, and provided a clear rationale. Your discussion ties CV accuracy to confidence, notes areas of agreement/disagreement, and offers plausible authorship conclusions. Solid interpretation aligned with your results.

---

### **Exercise 3: Working with decision trees** (10/10 = 100.0%)

**Part ex3-part1** (ex3-part1.fill): 2/2 points

_Feedback:_ Good job. You trained a DecisionTreeClassifier and reported 5-fold CV accuracy (on the train split) and test accuracy. This satisfies the task. Minor note: CV on the full dataset (X, y) was expected, but using X_train,y_train is a valid approach.

**Part ex3-part2** (ex3-part2.code): 2/2 points

_Feedback:_ Good work. You trained a DecisionTreeClassifier with max_depth=3 on the provided data and visualized it using plot_tree with feature and class names. The plot setup and display are correct. Full credit.

**Part ex3-part3** (ex3-part3.answer): 2/2 points

_Feedback:_ Good explanation of the root split: you identify f8, the threshold (~0.209), and why it’s chosen (max info gain/reduced impurity). For completeness, you could also note which side is mostly class 0 vs class 1, but your reasoning is correct.

**Part ex3-part4** (ex3-part4.code): 2/2 points

_Feedback:_ Well done. You train both trees (max_depth=None and 3), use 5-fold CV with StratifiedKFold on the training set, compute mean/std CV accuracy, and also report test accuracy for both—clear comparison. Meets the task requirements.

**Part ex3-part5** (ex3-part5.answer): 2/2 points

_Feedback:_ Correct: the depth-3 tree performs better due to reduced overfitting, as evidenced by higher test accuracy despite slightly better CV for the unrestricted tree. Clear reasoning about generalization and model simplicity. Nice tie-in to earlier split insight.

---

## Additional Information

This feedback was automatically generated by the autograder using LLM-based evaluation.

**Generated:** 2025-11-11 22:37:25 UTC

If you have questions about your grade, please reach out to the instructor.

---

*Powered by [Grade-Lite](https://github.com/your-repo/grade-lite) Autograder*