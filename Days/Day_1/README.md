DAY 1 (20/02/26) – Delta Conversion & Optimization

🛠️ Tasks

Convert raw CSV to Delta format

Read CSV files into a Spark DataFrame

Write them as a Delta table for ACID compliance

Create a managed Delta table

Register the table in the Unity Catalog or Metastore

Ensure it’s discoverable for queries

Append data multiple times

Simulate incremental loads

Observe how Delta handles small-file appends

Apply OPTIMIZE and observe improvement

Compact small files for better read performance

Compare query performance before and after optimization

✅ Notes

Delta tables support ACID transactions, so repeated writes won’t corrupt data.

Always drop or vacuum old data carefully to maintain performance.

Small-file simulation is useful for learning, but skip for very large files in production.
