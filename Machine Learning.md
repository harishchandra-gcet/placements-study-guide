© 2026 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# Machine Learning

## 1. Machine Learning Fundamentals

### Supervised vs. Unsupervised Learning

| Feature | Supervised Learning | Unsupervised Learning |
| --- | --- | --- |
| **Data** | Uses **Labeled** data (Input + Output). | Uses **Unlabeled** data (Input only). |
| **Goal** | To predict an outcome or classify data. | To find hidden patterns or structures. |
| **Applications** | Spam detection, Price prediction. | Customer segmentation, PCA. |

### Bias-Variance Tradeoff

* **Bias:** Error due to overly simplistic assumptions (e.g., using a linear model for non-linear data). Leads to **Underfitting**.
* **Variance:** Error due to the model being too sensitive to small fluctuations in the training set. Leads to **Overfitting**.
* **The Goal:** Minimize both errors to find the "Sweet Spot" where the model generalizes well to unseen data.



## 2. Core Algorithms

### Regression: Linear & Logistic

* **Linear Regression:** Predicts a continuous value. It assumes a linear relationship between input  and output .
* Equation: 


* **Logistic Regression:** Despite the name, it is a **Classification** algorithm. It uses the **Sigmoid function** to map outputs between 0 and 1.
* Equation: 



### Classification: SVM, Decision Trees, KNN

* **Support Vector Machine (SVM):** Finds the "Hyperplane" that maximizes the margin between two classes.
* **Decision Trees:** A tree-like structure where nodes represent features, branches represent rules, and leaves represent outcomes. It uses **Gini Impurity** or **Entropy** to decide where to split.
* **K-Nearest Neighbors (KNN):** A "lazy learner" that classifies a point based on the majority class of its  closest neighbors (usually using Euclidean distance).



## 3. Ensemble Methods

These methods combine multiple models to create a stronger, more robust model.

### Random Forest (Bagging)

**How it works:**

1. **Bootstrapping:** Creates multiple subsets of the original data with replacement.
2. **Feature Randomness:** Each tree in the forest is built using a random subset of features.
3. **Aggregation:** For classification, it takes the "Majority Vote"; for regression, it takes the "Average."

### XGBoost (Boosting)

**How it works:**
Unlike Random Forest (where trees grow in parallel), XGBoost grows trees **sequentially**. Each new tree attempts to correct the errors (residuals) made by the previous trees. It is highly efficient due to built-in regularization and parallel processing.



## 4. Model Evaluation & Tuning

### Evaluation Metrics

* **Accuracy:** . Good for balanced datasets.
* **Precision:** . Focuses on minimizing False Positives.
* **Recall:** . Focuses on minimizing False Negatives.
* **F1-Score:** The harmonic mean of Precision and Recall. Use this for **Imbalanced Datasets**.
* **ROC-AUC:** Measures the model's ability to distinguish between classes across different thresholds.

### Regularization (L1 & L2)

Regularization adds a penalty term to the cost function to prevent overfitting by discouraging overly complex models.

* **L1 Regularization (Lasso):** Adds the absolute value of coefficients. It can shrink some coefficients to **zero**, effectively performing feature selection.
* **L2 Regularization (Ridge):** Adds the squared value of coefficients. It shrinks coefficients but rarely to zero.


## Example Interview Q&A

> **Q: How does a Random Forest work?**
> **A:** It is an ensemble of Decision Trees. It uses "Bagging" (Bootstrap Aggregating) to train trees on different data subsets and "Feature Randomness" to ensure trees aren't highly correlated. The final output is the average or majority vote of all trees, which reduces variance and prevents overfitting.

> **Q: What is the difference between L1 and L2 regularization?**
> **A:** L1 (Lasso) adds a penalty equal to the absolute value of the coefficients, which can lead to sparse models where some feature weights become zero. L2 (Ridge) adds a penalty equal to the square of the coefficients, which keeps all features but minimizes their impact. L1 is better for feature selection.

> **Q: When would you use F1-Score instead of Accuracy?**
> **A:** When the classes are heavily imbalanced. For example, in fraud detection, 99% of transactions might be legitimate. A model that predicts "Not Fraud" for everything would have 99% accuracy but be useless. F1-Score accounts for both Precision and Recall, making it a better metric here.

> **Q: Explain the Bias-Variance tradeoff.**
> **A:** It’s the tension between a model's ability to minimize error from erroneous assumptions (Bias) and its sensitivity to noise in the training data (Variance). High bias leads to underfitting, while high variance leads to overfitting. We aim for a balance to achieve the lowest total error.
