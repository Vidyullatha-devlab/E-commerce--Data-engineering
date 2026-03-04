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


**Observations on Time Travel Retention**

Although no manual VACUUM command was executed during this exercise, the Delta table history showed a VACUUM operation triggered on the same day.

This resulted in older data files being permanently removed according to the default retention policy (7 days). As a result, time travel to very old versions (e.g., version 0) was not possible.

This highlights that:

Delta Lake retention policies govern recoverability.

Automated maintenance can remove historical data.

Version metadata may exist even if underlying files are deleted.

Time travel availability depends on file retention, not just version history.
Time travel is not infinite.

Delta Lake is not a magical archive.It is a versioned system with configurable retention.
