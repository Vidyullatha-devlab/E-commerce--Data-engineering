**DAY 5 – Production-Grade Feature Engineering**
**Objective**

Transform engineered user features into a supervised learning dataset.

**Create:**

binary purchase label

feature + label table

train/test split

distribution validation

**Architecture Context**

**Medallion Layers:**

Bronze → events
Silver → user features
Gold → ML dataset

**Day 5 expands Gold:**

**Gold ML → training-ready table**

The Gold ML table contains:

features

label

no leakage

consistent grain (user)

This is the dataset consumed by ML models.

**Learned Concepts:**
1.Target Creation (Binary Label)

Label definition:

purchased = 1 if user has at least one purchase event
purchased = 0 otherwise

2.Feature + Label Join

Join features and labels:

Used  inner join to ensures both feature and label exist

removes orphan rows

maintains dataset integrity

3.Train/Test Split

Reproducible split:

80% training

20% testing

deterministic via seed

This prevents data leakage and ensures repeatability.

4.Distribution Validation

Class imbalance is expected in ecommerce.

Example output:

purchased | count
1         | 9
0         | 70937

Observations:

purchases are rare

non-purchases dominate

accuracy alone is insufficient metric

ML systems must handle imbalance deliberately.
