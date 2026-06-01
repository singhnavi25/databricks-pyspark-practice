# Contributing

Thanks for your interest in contributing. All skill levels are welcome - whether you're fixing a typo, improving a test, or adding a whole new notebook.

---

## What You Can Contribute

- **New notebooks** - new datasets, topics, or difficulty levels not yet covered
- **New problems** - additional problems inside an existing notebook
- **Bug fixes** - incorrect test assertions, broken solution stubs, wrong expected columns
- **Hint notebooks** - hints for problems that don't have one yet
- **README / docs** - corrections, clearer wording, better examples

---

## Notebook Standards

Before submitting, make sure your notebook follows these conventions:

### Structure
Every notebook must have this layout, in order:
1. A title markdown cell with dataset, difficulty, and topics listed
2. A single setup cell with all imports and `spark.table(...)` calls - no imports scattered elsewhere
3. A `## Learn` markdown cell + a worked example code cell (see format below)
4. For each problem: a markdown cell, then a blank solution cell, then a test cell

### Learn cell format
Every notebook must have a `## Learn` section (two cells) immediately after the setup cell.
The markdown cell lists the key functions in a table with links to official Spark docs.
The code cell shows one runnable example using the **same dataset** as the notebook but operating on **different columns or operations** than any problem asks — it teaches the pattern without solving the problems.

```markdown
## Learn — [short topic name]

| Function | What it does |
|----------|-------------|
| `F.funcName(col)` | What it does in one line |

**Docs:** [Link text](url) · [Link text](url)
```

```python
# Run this example first — then solve the problems below.
# NOTE: this example is not a solution to any problem

df = spark.table("samples.catalog.table")
# ... 3-6 lines showing the pattern
```

### Problem format
```
## Problem N - Short title

Description of what to solve. Include:
- Key functions to use (without giving the answer away)
- Expected output columns listed explicitly

Assign result to: result_N
```

### Solution cell
```python
# Problem N - write your solution here
# Assign result to: result_N

result_N = None  # replace this
```

### Test cell
```python
# Tests for Problem N
assert result_N is not None, "result_N is None"
assert hasattr(result_N, 'columns'), "Must be a Spark DataFrame"
cols = [c.lower() for c in result_N.columns]
assert 'expected_col' in cols, "Missing column: expected_col"
cnt = result_N.count()
assert cnt > 0, "Got 0 rows"
print(f"Problem N passed ({cnt} rows)")
```

### Data sources
- Use only `samples.*` Unity Catalog tables - available in every Databricks workspace automatically
- For write-then-read exercises, use `/tmp/` paths only
- For inline test data, use `spark.createDataFrame([...], schema)` directly in the notebook
- No external files, no uploads, no custom datasets

### Style rules
- No hints inside practice notebooks - add hints to `hints/` only
- No em dashes (`-` not `-`) anywhere in text
- No references to any AI tools, assistants, or code generators
- All imports go in the single setup cell at the top
- Notebook must run cleanly from top to bottom with Run All

---

## Adding a Hint Notebook

Hints live in `hints/<Level>/<notebook_name>_hints.ipynb`. Structure:

```markdown
## Problem N

<details>
<summary>Hint 1</summary>

Your hint text here. Point toward the right function without giving the full solution.

</details>

<details>
<summary>Hint 2</summary>

A more specific hint if needed.

</details>
```

Only add hints where the key function or pattern is genuinely non-obvious. Not every problem needs a hint.

---

## How to Contribute

1. Fork the repository on GitHub
2. Create a branch: `git checkout -b add-streaming-notebook`
3. Make your changes following the standards above
4. Test that every cell in your notebook runs without error on a Databricks cluster (DBR 13.0+)
5. Open a pull request with a clear description of what you added or changed

### PR description should include
- What notebook(s) you changed or added
- Which dataset(s) the new content uses
- A brief note confirming you ran the notebook end-to-end successfully

---

## Reporting Issues

If you find a bug - broken test, wrong expected columns, a problem that has no solution possible - open a GitHub issue with:
- The notebook name and problem number
- What the error or problem is
- Your Databricks Runtime version if relevant

---

## Questions

Open a GitHub Discussion if you have questions about a problem, want feedback on a solution approach, or want to discuss a potential contribution before building it.
