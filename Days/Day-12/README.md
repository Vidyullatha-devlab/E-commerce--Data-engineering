**Day 12 – Cost Optimization Basics (Spark & Delta)**

**Objective**
Understand how Spark job execution impacts cost and learn practical techniques to reduce unnecessary compute usage.
In distributed systems, every action triggers a job, and every job consumes cluster resources. 
Cost optimization is about reducing redundant computation and minimizing data movement.

**Analyzing Job Runtime**
Observations:
  Each action triggers a separate Spark job.
  Re-running the same action executes a new DAG.
  Spark UI confirmed multiple jobs when redundant actions were executed.

 **Reducing Unnecessary Actions**
  Redundant actions → Multiple jobs
  Optimized version → Single job
Every Spark action = DAG execution and Fewer actions = lower compute cost

**Caching vs Recompute**
Tested execution  with and without caching.
Observations:
Caching improved performance when dataset was reused.
Caching is not beneficial if data is used only once.
Caching trades memory usage for faster repeated computation.

**Data Partitioning & Partition Pruning**

Checked execution plan for:
PartitionFilters
Reduced FileScan

Partition pruning reduces:
Disk I/O
Data scan size
Compute time

Lower I/O = lower cost.

**Small File Optimization**
Multiple writes create many small files.Used OPTIMIZE option.

After optimiztion:
Reduced number of files
Faster query performance
Small file problem increases metadata overhead and slows scans.

Cost optimization in Spark is not about syntax — it is about execution planning.
Understanding how Spark executes transformations and actions is critical for building efficient, production-ready data pipelines.
