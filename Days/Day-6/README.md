**DAY 6 – Model Training & Tuning**
**Objective**

Train predictive models on the Gold ML dataset and evaluate performance.

**Models:**

Logistic Regression (linear baseline)

RandomForest (nonlinear ensemble)

**Metrics:**

AUC (Area Under ROC Curve)

**Tuning:**

parameter experimentation

feature vectorization

evaluation comparison

**Concepts Learned**
1.Feature Vectorization:ML models expect a single feature vector.Spark’s MLlib uses VectorAssembler to combine columns.
2.Logistic Regression:Logistic Regression predicts probability of binary outcomes.
3.RandomForest :RandomForest is an ensemble of decision trees.
4.AUC Evaluation: It measures ranking ability:
1.0 → perfect
0.5 → random
0.7 → often acceptable in behavioral prediction
AUC is preferred under class imbalance.Accuracy may mislead.
