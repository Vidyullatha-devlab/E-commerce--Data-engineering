# 📅 Day 0 — Setup & Prerequisites

**Date:** Feb 18  
**Challenge:** 14-Day AI Challenge — Ecommerce Behavior Analytics

---

## ✅ Objectives Completed

1. Installed Kaggle CLI and downloaded dataset  
2. Stored dataset in **Unity Catalog Volume** (avoided DBFS root)  
3. Defined explicit Spark schema  
4. Loaded CSV into Spark DataFrame  
5. Validated schema and row count  
6. Cached dataset for optimization  

---

## ⚙️ Spark Schema Used

```python
from pyspark.sql.types import StructType, StructField, TimestampType, StringType, LongType, DoubleType

schema = StructType([
    StructField("event_time", TimestampType(), True),
    StructField("event_type", StringType(), True),
    StructField("product_id", LongType(), True),
    StructField("category_id", LongType(), True),
    StructField("category_code", StringType(), True),
    StructField("brand", StringType(), True),
    StructField("price", DoubleType(), True),
    StructField("user_id", LongType(), True),
    StructField("user_session", StringType(), True)
])

