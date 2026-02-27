**Day 7 – MLflow Tracking **
**Objective**

Day 7 introduces model lifecycle management using MLflow.
Instead of just training models, we:
✔ track experiments
✔ log metrics
✔ version models
✔ compare runs
✔ enable reproducibility
This is essential for production ML engineering.

What MLflow Does?

MLflow is a tracking and lifecycle platform.It records:
• parameters
• metrics
• artifacts
• model versions

Without tracking, experiments become unrepeatable.

**Architecture in Databricks**

In Databricks with Unity Catalog:

1.runs are stored in experiment workspace

2.artifacts require UC volume storage

3.models are versioned and governed

4.Require a temporary Spark storage for model artifacts.

**Key Concepts**
Experiment

A container for runs.

Created with:

mlflow.set_experiment("/Workspace/ecommerce_purchase_prediction")

If it doesn’t exist, MLflow creates it.

Run

A single experiment instance.

Created with:

with mlflow.start_run(run_name="Logistic_Baseline"):

Everything inside logs to that run.

Metrics

Performance values.

Example:

mlflow.log_metric("AUC", auc)

Used to compare models.

Parameters

Model configuration.

Example:

mlflow.log_param("numTrees", 100)

Documents how the model was built.

Artifact (Model)

The actual trained model.

Logged with:

mlflow.spark.log_model(
    model,
    "model",
    dfs_tmpdir="/Volumes/workspace/default/nameof the folder/"
)

This stores the model for later use.

Governance Requirement

Databricks serverless/shared clusters require UC volume paths for Spark model storage.

That’s why  used:

/Volumes/workspace/default/nameof the folde/

MLflow needs it for temporary model serialization.

Lifecycle Mindset

Training a model is easy.

Managing it is harder.

Production ML requires:

✔ reproducibility
✔ versioning
✔ governance
✔ experiment tracking

MLflow provides that ecosystem.
