# Curriculum roadmap & progress

This file is the source of truth for "where we are" in the course. The daily agent reads the **Progress** section below to know what was last covered, picks the next 1-2 topics from the **Roadmap**, advances the pointer, and commits the update alongside that day's question file.

## How to use this file (for the daily agent)

1. Read `Progress` → `last_topic_index` and `day_number`.
2. Today's primary topic = `Roadmap[last_topic_index + 1]` (wrap to the start of "Cycle 2: harder synthesis" once you run off the end of the list).
3. Every 5th day (`day_number % 5 == 0`) is a **review day**: instead of a new topic, write 5 questions that combine/contrast the last 4 topics covered (this is where "close options" distractors matter most — e.g. `.loc` vs `.iloc`, `merge` vs `join` vs `concat`, `axis=0` vs `axis=1`).
4. Read the last 3 files in `questions/` so new questions don't repeat old ones verbatim and can explicitly build on them (e.g. "yesterday you used `.groupby().sum()` — today add `.agg()` with multiple functions").
5. After writing today's question file, update `Progress` below: bump `day_number` by 1, set `last_topic_index` to the topic just covered, set `last_sent_date`, and append one line to the `Log`.

## Progress

- `day_number`: 3
- `last_topic_index`: 2
- `last_sent_date`: 2026-09-09
- `last_topic`: NumPy vectorized ops & broadcasting (Roadmap #3)

## Log

(newest entries at the bottom; one line per day, e.g. `Day 1 — 2026-09-08 — NumPy array creation & dtypes`)

Day 1 — 2026-09-07 — NumPy array creation & dtypes
Day 2 — 2026-09-08 — NumPy indexing & slicing (+ 2 reinforcement Qs on array dtype truncation)
Day 3 — 2026-09-09 — NumPy vectorized ops & broadcasting

## Roadmap — Cycle 1 (fundamentals, one topic builds on the last)

1. NumPy array creation & dtypes (`np.array`, `.dtype`, `.shape`, `.ndim`)
2. NumPy indexing & slicing (basic + fancy indexing, negative indices)
3. NumPy vectorized ops & broadcasting
4. NumPy aggregations (`sum`, `mean`, `min`/`max`, `axis=` parameter)
5. NumPy boolean masking & `np.where`
6. Pandas Series: creation, index, basic ops
7. Pandas DataFrame: creation from dict/list/np.array
8. Selection with `.loc` vs `.iloc`
9. Boolean filtering on a DataFrame (incl. combining conditions with `&`/`|`)
10. Adding/dropping columns & rows (`assign`, `drop`, `insert`)
11. Handling missing data (`isna`, `fillna`, `dropna`)
12. Sorting & ranking (`sort_values`, `sort_index`, `rank`)
13. GroupBy basics (`groupby().agg()/sum()/mean()`)
14. GroupBy with multiple keys & multiple aggregations
15. Merge/join/concat — differences and when to use each
16. `apply` / `map` / `applymap` and why to avoid them when a vectorized op exists
17. String methods via `.str` accessor
18. Datetime handling (`pd.to_datetime`, `.dt` accessor, resampling)
19. Pivot tables & `pd.crosstab`
20. Reshaping: `melt`, `pivot`, `stack`/`unstack`
21. MultiIndex basics
22. Window functions: `rolling`, `expanding`, `.shift()`, `.diff()`
23. Categorical dtype & memory/perf implications
24. Combining NumPy + pandas (`.to_numpy()`, applying ufuncs to a DataFrame)
25. Performance: vectorization vs `.apply()` vs `.iterrows()` (why iterrows is a trap)

## Roadmap — Cycle 2: harder synthesis (loops back here after topic 25)

26. Multi-step chained operations (filter → groupby → agg → sort in one chain)
27. `pivot_table` with custom `aggfunc` and multiple value columns
28. Advanced boolean indexing with `.isin()`, `~`, `.query()`
29. Merging with mismatched keys, `indicator=True`, validating merge cardinality
30. `groupby().transform()` vs `.agg()` vs `.apply()` — when each is required
31. Handling duplicate data (`duplicated`, `drop_duplicates`, subset logic)
32. Memory/dtype optimization (`downcast`, `category`, `astype`)
33. NumPy broadcasting edge cases & shape mismatches
34. NumPy linear algebra basics (`np.dot`, `@`, `np.linalg`)
35. Custom `.agg()` with named aggregations (`pd.NamedAgg`)
36. Time series resampling + rolling combined
37. Working with JSON/nested structures via `json_normalize`
38. Method chaining style vs step-by-step (readability/perf tradeoffs)
39. Common gotchas: `SettingWithCopyWarning`, views vs copies
40. Mixed review / "debug this snippet" style questions drawing on anything above

After topic 40, start a **Cycle 3** by repeating the roadmap but every question must be a "spot the bug" or "predict the exact output" style rather than "which command does X" — write new topics/entries here as that cycle is planned, don't just silently reuse Cycle 1/2 questions verbatim.
