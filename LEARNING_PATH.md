# Learning Path

> **Suggested progression for working through the 52 notebooks.**
> Each week builds on the last — don't skip ahead until the previous section feels natural.
>
> Workflow: **Try the problem → check the hint → read the docs → try again.**
> Only open the hint when you're genuinely stuck, not as a first step.

---

## Suggested Schedule

| Week | Notebooks | Focus | Est. Time |
|------|-----------|-------|-----------|
| 1 | Easy 01-05 | Loading tables, `filter`, `groupBy`, aggregations | ~3 hrs |
| 2 | Easy 06-10 | Dates, booleans, joins, multi-table queries | ~3 hrs |
| 3 | Easy 11-15 | Strings, datetime, nulls, column ops, set ops | ~4 hrs |
| 4 | Medium 01-05 | Window functions, running totals, rankings | ~4 hrs |
| 5 | Medium 06-10 | Star schema queries, anti-joins, multi-hop joins | ~4 hrs |
| 6 | Medium 11-15 | Advanced strings, arrays, pivot/unpivot, all join types, maps & structs | ~5 hrs |
| 7 | Medium 16-21 | AI functions, higher-order functions, datetime advanced, statistics | ~5 hrs |
| 8 | Hard 01-08 | Benchmark queries, PII masking, advanced analytics | ~5 hrs |
| 9 | Hard 09-13 | UDFs, performance tuning, SQL vs DataFrame API, capstone | ~5 hrs |
| 10 | Hard 14-16 | Delta Lake, read/write, utilities & security | ~4 hrs |

---

## Progress Checklist

### Easy (15 notebooks · 75 problems)

- [ ] Easy 01 — NYC Taxi Trips: filter, count, agg, sorting
- [ ] Easy 02 — Bakehouse Customers: groupBy, filter, distinct
- [ ] Easy 03 — Bakehouse Transactions: aggregation, date, groupBy
- [ ] Easy 04 — Bakehouse Franchises: groupBy, filter, count
- [ ] Easy 05 — TPC-H Customer: filter, aggregation, groupBy
- [ ] Easy 06 — TPC-H Orders: filter, date functions, groupBy
- [ ] Easy 07 — Wanderbricks Users: filter, boolean columns, date
- [ ] Easy 08 — Wanderbricks Bookings: filter, aggregation, date
- [ ] Easy 09 — TPC-H Nation & Region: joins, groupBy
- [ ] Easy 10 — Wanderbricks Properties: filter, aggregation
- [ ] Easy 11 — String Functions Basics: upper/lower, split, concat, length, substring
- [ ] Easy 12 — Datetime Functions Basics: year/month/hour, datediff, date_format
- [ ] Easy 13 — Null Handling: isNull, fillna, dropna, coalesce
- [ ] Easy 14 — Column Operations: withColumn, cast, when/otherwise, lit, expr
- [ ] Easy 15 — Set Operations: union, intersect, subtract, dropDuplicates

### Medium (21 notebooks · 150 problems)

- [ ] Medium 01 — NYC Taxi Analytics: window functions, running totals
- [ ] Medium 02 — Bakehouse Sales Analysis: complex aggregations
- [ ] Medium 03 — Bakehouse Customer Transactions: multi-table analysis
- [ ] Medium 04 — TPC-H Lineitem: large-scale aggregations
- [ ] Medium 05 — TPC-H Orders + Customers: star schema joins
- [ ] Medium 06 — Wanderbricks Reviews: text analysis, grouping
- [ ] Medium 07 — Wanderbricks Payments: payment analytics
- [ ] Medium 08 — TPC-DS Store Sales: retail data warehouse queries
- [ ] Medium 09 — Bakehouse Franchises + Sales: franchise analytics
- [ ] Medium 10 — Wanderbricks Bookings + Users: anti-joins, semi-joins
- [ ] Medium 11 — String Advanced: regexp_replace, regexp_extract, lpad, format_string
- [ ] Medium 12 — Array Functions: explode, collect_list/set, array_contains, flatten
- [ ] Medium 13 — Pivot and Unpivot: pivot, stack, crosstab
- [ ] Medium 14 — All Join Types: inner/left/right/full/semi/anti/cross, broadcast
- [ ] Medium 15 — Maps and Structs: create_map, map_from_entries, struct, to_json
- [ ] Medium 16 — Databricks AI Functions: ai_analyze_sentiment, ai_classify
- [ ] Medium 17 — Window Functions Advanced: dense_rank, ntile, percent_rank, lead/lag, rowsBetween
- [ ] Medium 18 — Higher-Order Functions: transform, filter, aggregate, zip_with, from_json
- [ ] Medium 19 — Datetime Advanced: unix_timestamp, add_months, last_day, timezone conversion
- [ ] Medium 20 — Statistical Aggregations: stddev, corr, percentile_approx, rollup, cube
- [ ] Medium 21 — Array and Map Extras: explode_outer, posexplode_outer, map_entries, str_to_map

### Hard (16 notebooks · 128 problems)

- [ ] Hard 01 — Advanced Analytics 1
- [ ] Hard 02 — Advanced Analytics 2
- [ ] Hard 03 — Complex Queries
- [ ] Hard 04 — TPC-H Benchmark 1
- [ ] Hard 05 — TPC-H Benchmark 2
- [ ] Hard 06 — TPC-H Benchmark 3
- [ ] Hard 07 — TPC-H Benchmark Queries
- [ ] Hard 08 — Wanderbricks Advanced BI
- [ ] Hard 09 — UDFs and Pandas UDFs: @udf, @pandas_udf, applyInPandas
- [ ] Hard 10 — Schema and Types: StructType, DDL schema, nested types
- [ ] Hard 11 — Performance: cache, repartition, broadcast, explain, salting
- [ ] Hard 12 — SQL vs DataFrame API: CTEs, spark.catalog, dynamic SQL
- [ ] Hard 13 — Capstone: end-to-end pipeline with window, PII, collect_set
- [ ] Hard 14 — Delta Lake: write/read, append, update, delete, merge, time travel
- [ ] Hard 15 — Reading and Writing Data: CSV, JSON, Parquet, partitionBy, saveAsTable
- [ ] Hard 16 — Utilities and Security: hashing, encoding, mapInPandas, repartitionByRange

---

## Key Resources

Keep these open in a second tab while you work:

| Resource | What's in it |
|----------|-------------|
| [PySpark Functions](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/functions.html) | All `F.*` functions with signatures and examples |
| [DataFrame API](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/dataframe.html) | All DataFrame methods |
| [Databricks PySpark Guide](https://docs.databricks.com/en/pyspark/index.html) | Databricks-specific patterns and best practices |
| [Delta Lake Guide](https://docs.databricks.com/en/delta/index.html) | Everything for Hard 14 |
| [Databricks AI Functions](https://docs.databricks.com/en/large-language-models/ai-functions.html) | Reference for Medium 16 |

---

## Tips

- **Easy 01-10** are intentionally repetitive — the same `groupBy` + `agg` + `orderBy` pattern appears many times. That repetition is deliberate; fluency comes from doing it on 10 different datasets.
- **Medium 17** (Window Functions Advanced) is the hardest jump in the whole collection. Take extra time there before moving on.
- **Hard 13** (Capstone) synthesises everything from Medium and Hard — don't attempt it before finishing Hard 09-12.
- Each notebook has a `## Learn` section at the top with a runnable example. Run it before attempting Problem 1.
