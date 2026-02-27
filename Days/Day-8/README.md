**Day 8 – Batch Inference Pipeline** 
**Objective**

Today learning shifts from training to production scoring.

The goal is to:

->score all users using the trained model
->generate purchase probability predictions
->store results in a Delta Gold predictions table
->identify top potential buyers

This is the foundation of batch inference in ML systems.

What Is Batch Inference?

Batch inference applies a trained model to a dataset at scale.

Instead of scoring one request at a time (online inference), we:

score users in bulk

schedule periodic runs

store predictions for downstream use

**Batch vs Online Inference**

batch → periodic scoring of many users

online → real-time scoring of single requests

Batch is simpler and common for marketing and analytics.

Inference uses same feature columns as training.

VectorAssembler creates:

features vector

which models require.

Consistency prevents schema mismatch.

Prediction tables are separate from feature tables.

This separation enables:

auditability

lifecycle management

clear data lineage

**Business Impact**

Predictions enable:

✔ targeting high-probability users
✔ prioritizing marketing
✔ data-driven decisions

Models inform actions, not certainties.
Production ML requires governance.
