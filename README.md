# PySpark Practice - Databricks Notebook Collection

A structured collection of **52 notebooks** and **360 hands-on problems** covering PySpark from beginner to advanced, all powered by the `samples` catalog built into every Databricks workspace - no external data needed.

## Structure

```
notebooks/
├── Easy/       15 notebooks · 75 problems   - fundamentals, strings, dates, nulls, set ops
├── Medium/     21 notebooks · 147 problems  - window functions, joins, arrays, maps, higher-order functions, stats, datetime, AI functions
└── Hard/       16 notebooks · 128 problems  - UDFs, performance, Delta Lake, read/write, utilities, security, SQL, capstone

hints/
├── Easy/       hint notebooks for Easy problems that have hints available
├── Medium/     hint notebooks for Medium problems that have hints available
└── Hard/       hint notebooks for Hard problems that have hints available
```

Each practice notebook is self-contained:
- **Problem statement** - what to solve and why it matters
- **Solution cell** - blank, you write your code here
- **Test cell** - pre-written assertions that validate your answer automatically

### How hints work

Practice notebooks contain **no hints** - the goal is for you to figure it out.
If you're stuck, open the matching `hints/` notebook for that section.
Hints are wrapped in collapsible `<details>` blocks so you reveal only what you need:

```
hints/Hard/09_udfs_and_pandas_udfs_hints.ipynb
  └── Problem 1
        └── <details> Hint 1  ← click to reveal
  └── Problem 4
        └── <details> Hint 1
        └── <details> Hint 2
```

Not every problem has a hint - only problems where the key function or pattern is non-obvious.

---

## Option 1 - Clone via Databricks Git (Repos)

The simplest way. Works on any Databricks plan including Community Edition.

1. Open your Databricks workspace
2. Go to **Workspace → Repos → Add Repo**
3. Paste the repo URL and click **Create Repo**
4. Navigate into `notebooks/Easy/` and open any notebook
5. Attach a cluster, open a notebook, write your solution, run the test cell

> **Cluster note:** Any cluster running **Databricks Runtime 13.0+** works. The `samples` catalog is available on all runtimes.

---

## Option 2 - Databricks Asset Bundles (DABs)

DABs let you deploy the notebooks as a managed project with CI/CD support. Use this if you want to track solutions in a team, run validation pipelines, or deploy to multiple workspaces.

### Prerequisites

```bash
# Install the Databricks CLI (v0.200+)
curl -fsSL https://raw.githubusercontent.com/databricks/setup-cli/main/install.sh | sh

# Authenticate
databricks auth login --host https://<your-workspace>.azuredatabricks.net
```

### Project setup

Create a `databricks.yml` in the repo root:

```yaml
bundle:
  name: pyspark-practice

targets:
  dev:
    mode: development
    default: true
    workspace:
      host: https://<your-workspace>.azuredatabricks.net

resources:
  jobs:
    validate_easy:
      name: "Validate Easy Notebooks"
      tasks:
        - task_key: easy_01
          notebook_task:
            notebook_path: ./notebooks/Easy/01_nyctaxi_trips_basics.ipynb
            source: WORKSPACE
          new_cluster:
            spark_version: "15.4.x-scala2.12"
            node_type_id: m5d.large
            num_workers: 1
```

### Deploy and run

```bash
# Validate the bundle config
databricks bundle validate

# Deploy notebooks to your workspace
databricks bundle deploy --target dev

# Run a specific job
databricks bundle run validate_easy --target dev
```

### Import notebooks manually via CLI

If you just want to upload without DABs:

```bash
# Import the entire notebooks folder into your workspace
databricks workspace import-dir ./notebooks /Users/<your-email>/pyspark-practice --overwrite
```

---

## Option 3 - Community Edition (no Git access)

If you're on Databricks Community Edition and don't have Repos access:

1. Download this repo as a ZIP from GitHub
2. In Databricks, go to **Workspace → Import**
3. Upload the `.ipynb` files one by one (or zip the folder and import as a directory)
4. Open any notebook and attach the free Community cluster

---

## Prerequisites

| Requirement | Details |
|---|---|
| Databricks workspace | Any tier - Community Edition works |
| Cluster runtime | DBR 13.0+ (Photon optional) |
| `samples` catalog | Available by default in all Databricks workspaces |
| No external data | Everything reads from `samples.*` Unity Catalog tables |

---

## Topic Coverage

| Notebook | Topics |
|---|---|
| Easy 01–10 | filter, groupBy, aggregation, joins, dates, sorting |
| Easy 11 | String basics - upper/lower/split/concat/length/substring |
| Easy 12 | DateTime - year/month/hour/datediff/date_format/date_trunc |
| Easy 13 | Null handling - isNull, fillna, dropna, coalesce |
| Easy 14 | Column ops - withColumn, cast, when/otherwise, lit, expr |
| Easy 15 | Set operations - union, intersect, subtract, dropDuplicates |
| Medium 01–10 | Window functions, running totals, star schema, anti-joins |
| Medium 11 | String advanced - regexp_replace, regexp_extract, lpad, format_string |
| Medium 12 | Array functions - explode, collect_list/set, array_contains, flatten |
| Medium 13 | Pivot & Unpivot - pivot, stack, crosstab |
| Medium 14 | All join types - inner/left/right/full/semi/anti/cross + broadcast |
| Medium 15 | Maps & Structs - create_map, map_from_entries, struct, to_json |
| Medium 16 | Databricks AI Functions - ai_analyze_sentiment, ai_classify, topic heatmap *(Databricks only)* |
| Medium 17 | Window Functions Advanced - dense_rank, ntile, percent_rank, cume_dist, lead, rowsBetween, rangeBetween |
| Medium 18 | Higher-Order Functions - transform, filter, aggregate, exists, forall, zip_with, from_json, map_keys/values |
| Hard 01–08 | Benchmark queries, PII masking, advanced analytics, BI |
| Hard 09 | UDFs & Pandas UDFs - @udf, @pandas_udf, applyInPandas |
| Hard 10 | Schema & Types - StructType, DDL schema, nested types |
| Hard 11 | Performance - cache, repartition, broadcast, explain, salting |
| Hard 12 | SQL vs DataFrame API - CTEs, spark.catalog, dynamic SQL |
| Hard 13 | Capstone - bakehouse end-to-end: stats loop, window+map, top-N+collect_set, PII dashboard |
| Hard 14 | Delta Lake - write/read, append, update, delete, merge/upsert, time travel, history, schema evolution |
| Hard 15 | Reading and Writing Data - CSV, JSON, Parquet, options, schemas, partitionBy, saveAsTable |
| Hard 16 | Utilities and Security - concat_ws, ltrim, rtrim, levenshtein, md5, sha2, crc32, base64, nanvl, nullif, monotonically_increasing_id, mapInPandas, crossJoin, exceptAll, intersectAll, createGlobalTempView, repartitionByRange |
| Medium 19 | DateTime Advanced - current_timestamp, to_timestamp, unix_timestamp, date_sub, add_months, last_day, next_day, timezone conversion, tumbling windows |
| Medium 20 | Statistical Aggregations - approx_count_distinct, stddev, variance, corr, percentile_approx, skewness, kurtosis, rollup, cube |
| Medium 21 | Array and Map Extras - explode_outer, posexplode_outer, array_remove, array_position, arrays_overlap, map_entries, map_filter, str_to_map, named_struct, json_tuple |

---

## Datasets Used

All data is in the `samples` catalog - available in every Databricks workspace automatically.

| Schema | Tables | Domain |
|---|---|---|
| `samples.nyctaxi` | `trips` | NYC taxi ride data |
| `samples.bakehouse` | 6 tables | Bakery franchise sales, customers, reviews |
| `samples.tpch` | 8 tables | TPC-H supply chain benchmark |
| `samples.tpcds_sf1` | 24 tables | TPC-DS retail data warehouse benchmark |
| `samples.wanderbricks` | 16 tables | Airbnb-style rental platform |

---

## How Each Notebook Works

```
┌─────────────────────────────────────────────┐
│  ## Problem N                               │  ← Read the problem
│  Clear description + expected columns       │
└─────────────────────────────────────────────┘
┌─────────────────────────────────────────────┐
│  result_N = None  # replace this           │  ← Write your PySpark code
└─────────────────────────────────────────────┘
┌─────────────────────────────────────────────┐
│  assert result_N is not None                │  ← Run this - instant feedback
│  assert 'column' in result_N.columns        │
│  print("Problem N passed ✓")               │
└─────────────────────────────────────────────┘
```
