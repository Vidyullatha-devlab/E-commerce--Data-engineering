**Day 11 – Time Travel & Data Recovery**

**Objective**
   Understand how Delta Lake enables:
   Versioning
   Rollback
   Data recovery

Delta tables maintain transaction history. Every write creates a new version.You can query older versions of the data without restoring backups.
This is called Time Travel.

Delta Lake provides:
  Snapshot isolation
  ACID transactions
  Built-in audit trail
  Time travel querying
  Easy recovery
Traditional data lakes cannot do this without manual backups.

Time travel is critical for:
Debugging pipeline failures,Reproducing ML training datasets,Compliance auditing,Undoing accidental deletes,Data governance
