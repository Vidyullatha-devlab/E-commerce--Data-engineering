**Day 10 – Query Optimization & Explain Plans**
**Objective**

Improve Spark performance by:

✔ analyzing execution plans
✔ leveraging partition pruning
✔ caching data
✔ comparing execution time

This is performance engineering for data pipelines.

**Explain Plan (.explain())**
Explain plan reveals how queries execute.
It shows:logical plan,physical plan,filters,shuffles
Insight:
If filter appears before scan → partition pruning works.
If full scan → optimization opportunity.

FileScan → efficient disk read

Shuffle → expensive data movement

Broadcast Join → good for small tables

Full Scan → candidate for partitioning

Explain plans expose these behaviors.

**Partition Pruning**
Partition pruning means Spark reads only relevant partitions.
Explain plan will confirm pruning.Without it, Spark scans everything (slow).

**Caching**
Caching stores data in memory for reuse.Memory access is faster than disk which is an optimization benefit.
Use when:
dataset queried repeatedly
iterative analytics
ML pipelines
