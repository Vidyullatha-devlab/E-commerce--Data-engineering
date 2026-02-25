**Day 4 – Micro-Batch Streaming with Delta Lake**
**Objective**

Extend the Medallion architecture to support incremental ingestion using Structured Streaming.

Instead of loading static CSV files in batch mode, we treat a folder as a streaming source and write new data incrementally into the Bronze Delta table.

This simulates real-world event ingestion while operating within cluster limitations.

**Architecture Context**

**Existing Pipeline**:

Bronze → workspace.ecommerce.events_delta
Silver → user-level aggregations
Gold → business-ready features

**Day 4 Enhancement:**

Streaming Folder → Bronze (Delta) → Silver → Gold

Streaming feeds the same Bronze table used in batch.

This demonstrates Lakehouse unification: batch and streaming share storage.

**Concepts Learned :**
Micro-Batch Streaming

Structured Streaming processes data in small incremental batches.

Instead of processing the entire dataset:

Spark monitors a folder

Detects new files

Processes only new data

Appends results into Delta

Checkpointing

Streaming requires a checkpoint location:

/Volumes/workspace/ecommerce/stream_volume/checkpoints/bronze

**Checkpoint stores:
**
processed file metadata

offsets

streaming state

This ensures:

no duplicate processing

recovery after failure

exactly-once guarantees with Delta

Without checkpointing, streaming is unreliable.

**Streaming → Delta Integration**

Delta Lake supports both batch and streaming writes.

Streaming writes append new rows to the Bronze table.

Batch queries can simultaneously read the same table.

Delta ensures:

ACID transactions

consistent snapshots

no partial reads

**Unity Catalog enforces:**

Catalog → Schema → Volume → Files

Storage must be registered and governed.

However there are certain Cluster Limitation & Trigger Behavior in free databricks trail account:

The cluster does not support infinite ProcessingTime triggers.

Therefore:

Continuous streaming is not available

Micro-batch execution mode is used

Stream processes available files and stops
