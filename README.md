# PySpark Practice - Databricks Notebook Collection

> **54 notebooks | 367 problems | Beginner to Advanced | Zero setup**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Databricks](https://img.shields.io/badge/Databricks-Runtime%2013.0%2B-red)](https://databricks.com)
[![PySpark](https://img.shields.io/badge/PySpark-3.x%2B-orange)](https://spark.apache.org/docs/latest/api/python/)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)

A structured collection of **54 notebooks** and **367 hands-on PySpark problems** covering Apache Spark from beginner to advanced, all powered by the `samples` catalog built into every Databricks workspace - no external data, no setup, no uploads needed.

**Who is this for?**
- Developers learning PySpark and Apache Spark for the first time
- Data engineers preparing for Databricks certifications
- Experienced engineers wanting structured practice on specific topics
- Teams onboarding new members to Spark-based data pipelines

---

## What's Covered

Every major PySpark concept from the DataFrame API to Delta Lake:

| Area | Functions and Concepts |
|---|---|
| DataFrame API | select, filter, groupBy, agg, join, window, withColumn, cast, when |
| String functions | regexp_replace, regexp_extract, concat_ws, lpad, levenshtein, format_string |
| Date and time | to_timestamp, unix_timestamp, date_add, date_sub, add_months, timezone conversion, tumbling windows |
| Array functions | explode, explode_outer, collect_list, flatten, transform, filter, aggregate, zip_with |
| Map and struct | create_map, map_from_entries, map_entries, map_filter, named_struct, str_to_map |
| JSON | from_json, to_json, get_json_object, json_tuple, schema_of_json |
| Window functions | rank, dense_rank, ntile, percent_rank, cume_dist, lag, lead, rowsBetween, rangeBetween |
| Joins | inner, left, right, full outer, semi, anti, cross, broadcast |
| Pivot and unpivot | pivot, stack, crosstab |
| Statistics | stddev, variance, corr, percentile_approx, skewness, kurtosis, rollup, cube |
| UDFs | @udf, @pandas_udf, applyInPandas, mapInPandas |
| Schema | StructType, StructField, ArrayType, MapType, nested types, DDL strings |
| Performance | cache, persist, repartition, coalesce, broadcast, explain, salting, predicate pushdown |
| Delta Lake | write, append, update, delete, merge/upsert, time travel, DESCRIBE HISTORY, schema evolution |
| SQL | spark.sql, CTEs, window SQL, subqueries, createGlobalTempView, spark.catalog |
| Read and write | CSV, JSON, Parquet with options, partitionBy, saveAsTable, schema inference |
| Security | md5, sha2, crc32, base64, PII masking patterns |
| Databricks AI | ai_analyze_sentiment, ai_classify *(Databricks only)* |

---

## Structure

```
notebooks/
├── Easy/       15 notebooks · 75 problems   - fundamentals, strings, dates, nulls, set ops
├── Medium/     21 notebooks · 150 problems  - window functions, joins, arrays, maps, higher-order functions, stats, datetime, AI functions
└── Hard/       18 notebooks · 142 problems  - UDFs, performance, Delta Lake, read/write, utilities, security, SQL, capstones

hints/
├── Easy/       hint notebooks for all 15 Easy notebooks
├── Medium/     hint notebooks for Medium problems that have hints available
└── Hard/       hint notebooks for Hard problems that have hints available

solutions/
└── Easy/       reference solutions for all 15 Easy notebooks (open only after a genuine attempt)
```

Each practice notebook is self-contained and follows this layout:

1. **`## Learn` section** - a function reference table with official Spark doc links, plus a small runnable worked example you can run before attempting the problems
2. **Problem statement** - what to solve and expected output columns
3. **Solution cell** - blank, you fill this in
4. **Test cell** - pre-written assertions that validate your answer automatically

### Suggested workflow

**Learn → Try → Hint → Docs → Solve → Reference**

1. Run the `## Learn` cell at the top of the notebook to see the pattern
2. Attempt the problem
3. If stuck, open the matching `hints/` notebook and reveal one hint at a time
4. If still stuck, follow the doc links in the `## Learn` section
5. Once you have a working solution, compare it against `solutions/` to see the reference approach and the `# Why:` explanation

### How hints work

Practice notebooks contain no hints - the goal is for you to work it out.
If you're stuck, open the matching `hints/` notebook for that section.
Hints are wrapped in collapsible `<details>` blocks so you reveal only what you need:

```
hints/Hard/09_udfs_and_pandas_udfs_hints.ipynb
  └── Problem 1
        └── <details> Hint 1  <- click to reveal
  └── Problem 4
        └── <details> Hint 1
        └── <details> Hint 2
```

Not every problem has a hint - only problems where the key function or pattern is non-obvious.

### Learning path

See [LEARNING_PATH.md](LEARNING_PATH.md) for a suggested week-by-week progression through all 52 notebooks, time estimates, and a progress checklist you can tick off as you go.

---

## Getting Started

### Option 1 - Databricks Git Repos (recommended)

The simplest way. Works on any Databricks plan including Community Edition.

1. Open your Databricks workspace
2. Go to **Workspace → Repos → Add Repo**
3. Paste this repo URL and click **Create Repo**
4. Open any notebook in `notebooks/Easy/`
5. Attach a cluster, write your solution, run the test cell

> Any cluster running **Databricks Runtime 13.0+** works. The `samples` catalog is available on all runtimes.

### Option 2 - Community Edition (no Git access)

1. Download this repo as a ZIP from GitHub
2. In Databricks, go to **Workspace → Import**
3. Upload the `.ipynb` files one by one (or zip the folder and import as a directory)
4. Open any notebook and attach the free Community cluster

### Option 3 - Databricks Asset Bundles (DABs)

For teams who want CI/CD and deployment pipelines:

```bash
# Install Databricks CLI
curl -fsSL https://raw.githubusercontent.com/databricks/setup-cli/main/install.sh | sh

# Authenticate
databricks auth login --host https://<your-workspace>.azuredatabricks.net

# Deploy
databricks bundle deploy --target dev
```

---

## Prerequisites

| Requirement | Details |
|---|---|
| Databricks workspace | Any tier - Community Edition works |
| Cluster runtime | DBR 13.0+ (Photon optional) |
| `samples` catalog | Available by default in all Databricks workspaces |
| External data files | None - everything reads from `samples.*` Unity Catalog tables |

---

## Datasets

All data is in the `samples` catalog - available in every Databricks workspace automatically. No uploads or downloads required.

| Schema | Tables | Domain |
|---|---|---|
| `samples.nyctaxi` | `trips` | NYC taxi ride data |
| `samples.bakehouse` | 6 tables | Bakery franchise sales, customers, reviews |
| `samples.tpch` | 8 tables | TPC-H supply chain benchmark |
| `samples.tpcds_sf1` | 24 tables | TPC-DS retail data warehouse benchmark |
| `samples.wanderbricks` | 16 tables | Airbnb-style rental platform |

---

## Full Topic Coverage

| Notebook | Topics |
|---|---|
| Easy 01-10 | filter, groupBy, aggregation, joins, dates, sorting |
| Easy 11 | String basics - upper/lower/split/concat/length/substring |
| Easy 12 | DateTime - year/month/hour/datediff/date_format/date_trunc |
| Easy 13 | Null handling - isNull, fillna, dropna, coalesce |
| Easy 14 | Column ops - withColumn, cast, when/otherwise, lit, expr |
| Easy 15 | Set operations - union, intersect, subtract, dropDuplicates |
| Medium 01-10 | Window functions, running totals, star schema, anti-joins |
| Medium 11 | String advanced - regexp_replace, regexp_extract, lpad, format_string |
| Medium 12 | Array functions - explode, collect_list/set, array_contains, flatten |
| Medium 13 | Pivot and Unpivot - pivot, stack, crosstab |
| Medium 14 | All join types - inner/left/right/full/semi/anti/cross + broadcast |
| Medium 15 | Maps and Structs - create_map, map_from_entries, struct, to_json |
| Medium 16 | Databricks AI Functions - ai_analyze_sentiment, ai_classify *(Databricks only)* |
| Medium 17 | Window Functions Advanced - dense_rank, ntile, percent_rank, cume_dist, lead, rowsBetween, rangeBetween |
| Medium 18 | Higher-Order Functions - transform, filter, aggregate, exists, forall, zip_with, from_json |
| Medium 19 | DateTime Advanced - current_timestamp, unix_timestamp, date_sub, add_months, last_day, timezone conversion |
| Medium 20 | Statistical Aggregations - approx_count_distinct, stddev, corr, percentile_approx, rollup, cube |
| Medium 21 | Array and Map Extras - explode_outer, posexplode_outer, array_remove, map_entries, map_filter, str_to_map |
| Hard 01-08 | Benchmark queries, PII masking, advanced analytics, BI reporting |
| Hard 09 | UDFs and Pandas UDFs - @udf, @pandas_udf, applyInPandas |
| Hard 10 | Schema and Types - StructType, DDL schema, nested types |
| Hard 11 | Performance - cache, repartition, broadcast, explain, salting |
| Hard 12 | SQL vs DataFrame API - CTEs, spark.catalog, dynamic SQL |
| Hard 13 | Capstone - end-to-end: stats loop, window+map, top-N+collect_set, PII dashboard |
| Hard 14 | Delta Lake - write/read, append, update, delete, merge/upsert, time travel, schema evolution |
| Hard 15 | Reading and Writing Data - CSV, JSON, Parquet, options, partitionBy, saveAsTable |
| Hard 16 | Utilities and Security - hashing, encoding, metadata functions, mapInPandas, repartitionByRange |
| Hard 17 | Capstone: TPC-H Supply Chain - linked problems across all 8 TPC-H tables (geography → revenue → late deliveries → supplier ranking → discount impact → full order report) |
| Hard 18 | Capstone: Wanderbricks Platform - linked problems across bookings, hosts, properties, reviews, payments (host portfolio → revenue → guest behaviour → review quality → cancellations → seasonal patterns → host dashboard) |

---

## How Each Notebook Works

```
+---------------------------------------------+
|  ## Problem N                               |  <- Read the problem
|  Clear description + expected columns       |
+---------------------------------------------+
+---------------------------------------------+
|  result_N = None  # replace this           |  <- Write your PySpark code
+---------------------------------------------+
+---------------------------------------------+
|  assert result_N is not None                |  <- Run this - instant feedback
|  assert 'column' in result_N.columns        |
|  print("Problem N passed")                  |
+---------------------------------------------+
```

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for notebook standards, structure guidelines, and how to submit a pull request.

---

## License

[MIT](LICENSE)
