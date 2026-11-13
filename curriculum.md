# Curriculum roadmap & progress

This file is the source of truth for "where we are" in the course. The daily agent reads the **Progress** section below to know what was last covered, picks the next 1-2 topics from the **Roadmap**, advances the pointer, and commits the update alongside that day's question file.

## How to use this file (for the daily agent)

1. Read `Progress` → `last_topic_index` and `day_number`.
2. Today's primary topic = `Roadmap[last_topic_index + 1]` (wrap to the start of "Cycle 2: harder synthesis" once you run off the end of the list).
3. Every 5th day (`day_number % 5 == 0`) is a **review day**: instead of a new topic, write 5 questions that combine/contrast the last 4 topics covered (this is where "close options" distractors matter most — e.g. `.loc` vs `.iloc`, `merge` vs `join` vs `concat`, `axis=0` vs `axis=1`).
4. Read the last 3 files in `questions/` so new questions don't repeat old ones verbatim and can explicitly build on them (e.g. "yesterday you used `.groupby().sum()` — today add `.agg()` with multiple functions").
5. After writing today's question file, update `Progress` below: bump `day_number` by 1, set `last_topic_index` to the topic just covered, set `last_sent_date`, and append one line to the `Log`.

## Progress

- `day_number`: 50
- `last_topic_index`: 40
- `last_sent_date`: 2026-11-13
- `last_topic`: Review day (Roadmap #37-40) — closes Cycle 2; Cycle 3 roadmap (topics 41-80, spot-the-bug/predict-output style) now planned below

## Log

(newest entries at the bottom; one line per day, e.g. `Day 1 — 2026-09-08 — NumPy array creation & dtypes`)

Day 1 — 2026-09-07 — NumPy array creation & dtypes
Day 2 — 2026-09-08 — NumPy indexing & slicing (+ 2 reinforcement Qs on array dtype truncation)
Day 3 — 2026-09-09 — NumPy vectorized ops & broadcasting
Day 4 — 2026-09-10 — NumPy aggregations (sum, mean, min/max, axis=)
Day 5 — 2026-09-11 — Review day (combining Roadmap #1-4: dtypes, indexing, broadcasting, aggregations)
Day 6 — 2026-09-14 — NumPy boolean masking & np.where
Day 7 — 2026-09-15 — Pandas Series: creation, index, basic ops
Day 8 — 2026-09-16 — Pandas DataFrame: creation from dict/list/np.array
Day 9 — 2026-09-17 — Selection with .loc vs .iloc
Day 10 — 2026-09-18 — Review day (combining Roadmap #5-8: boolean masking/np.where, Series, DataFrame creation, .loc vs .iloc)
Day 11 — 2026-09-21 — Boolean filtering on a DataFrame (combining conditions with &/|)
Day 12 — 2026-09-22 — Adding/dropping columns & rows (assign, drop, insert)
Day 13 — 2026-09-23 — Handling missing data (isna, fillna, dropna)
Day 14 — 2026-09-24 — Sorting & ranking (sort_values, sort_index, rank)
Day 15 — 2026-09-25 — Review day (combining Roadmap #9-12: boolean filtering, add/drop columns & rows, missing data, sorting & ranking)
Day 16 — 2026-09-28 — GroupBy basics (groupby().agg()/sum()/mean())
Day 17 — 2026-09-29 — GroupBy with multiple keys & multiple aggregations
Day 18 — 2026-09-30 — Merge/join/concat — differences and when to use each
Day 19 — 2026-10-01 — apply / map / applymap and why to avoid them when a vectorized op exists
Day 20 — 2026-10-02 — Review day (combining Roadmap #13-16: GroupBy basics, GroupBy multiple keys & aggregations, merge/join/concat, apply/map/applymap)
Day 21 — 2026-10-05 — String methods via .str accessor
Day 22 — 2026-10-06 — Datetime handling (pd.to_datetime, .dt accessor, resampling)
Day 23 — 2026-10-07 — Pivot tables & pd.crosstab
Day 24 — 2026-10-08 — Reshaping: melt, pivot, stack/unstack
Day 25 — 2026-10-09 — Review day (combining Roadmap #17-20: string methods via .str, datetime handling, pivot tables/crosstab, reshaping melt/pivot/stack/unstack)
Day 26 — 2026-10-12 — MultiIndex basics
Day 27 — 2026-10-13 — Window functions: rolling, expanding, .shift(), .diff()
Day 28 — 2026-10-14 — Categorical dtype & memory/perf implications
Day 29 — 2026-10-15 — Combining NumPy + pandas (.to_numpy(), applying ufuncs to a DataFrame)
Day 30 — 2026-10-16 — Review day (combining Roadmap #21-24: MultiIndex basics, window functions, categorical dtype, combining NumPy+pandas)
Day 31 — 2026-10-19 — Performance: vectorization vs .apply() vs .iterrows() (why iterrows is a trap)
Day 32 — 2026-10-20 — Multi-step chained operations (filter → groupby → agg → sort in one chain)
Day 33 — 2026-10-21 — pivot_table with custom aggfunc and multiple value columns
Day 34 — 2026-10-22 — Advanced boolean indexing with .isin(), ~, .query()
Day 35 — 2026-10-23 — Review day (combining Roadmap #25-28: performance vectorization vs apply/iterrows, multi-step chained operations, pivot_table custom aggfunc, advanced boolean indexing)
Day 36 — 2026-10-26 — Merging with mismatched keys, indicator=True, validating merge cardinality
Day 37 — 2026-10-27 — groupby().transform() vs .agg() vs .apply() — when each is required
Day 38 — 2026-10-28 — Handling duplicate data (duplicated, drop_duplicates, subset logic)
Day 39 — 2026-10-29 — Memory/dtype optimization (downcast, category, astype)
Day 40 — 2026-10-30 — Review day (combining Roadmap #29-32: merge mismatched keys/indicator/validate, groupby transform vs agg vs apply, duplicate handling, memory/dtype optimization)
Day 41 — 2026-11-02 — NumPy broadcasting edge cases & shape mismatches (note: corrected `last_topic_index` pointer from 31 to 32 before advancing — Day 40's review covered through Roadmap #32, so today correctly starts at #33 rather than repeating #32)
Day 42 — 2026-11-03 — NumPy linear algebra basics (np.dot, @, np.linalg)
Day 43 — 2026-11-04 — Custom .agg() with named aggregations (pd.NamedAgg)
Day 44 — 2026-11-05 — Time series resampling + rolling combined
Day 45 — 2026-11-06 — Review day (combining Roadmap #33-36: NumPy broadcasting edge cases & shape mismatches, NumPy linear algebra basics, custom .agg() named aggregations, time series resampling + rolling combined)
Day 46 — 2026-11-09 — Working with JSON/nested structures via json_normalize (Roadmap #37)
Day 47 — 2026-11-10 — Method chaining style vs step-by-step (readability/perf tradeoffs) (Roadmap #38)
Day 48 — 2026-11-11 — Common gotchas: SettingWithCopyWarning/ChainedAssignmentError, views vs copies (Roadmap #39, verified live against installed pandas 3.0.5 Copy-on-Write behavior)
Day 49 — 2026-11-12 — Mixed review: merge/validate/isin, groupby agg vs transform index-alignment bug, str+datetime pivot, broadcasting shape mismatch, duplicates vs chained-assignment contrast (Roadmap #40 — completes Cycle 2; next run should plan Cycle 3 per the note below, all questions "spot the bug"/"predict output" style, verified live against installed pandas 3.0.5 / numpy 2.5.3)
Day 50 — 2026-11-13 — Review day (combining Roadmap #37-40: json_normalize record_path/meta, method chaining broken by inplace=True, fancy-vs-basic .iloc views/copies under Copy-on-Write, merge validate many_to_one vs one_to_one) — completes Cycle 2; Cycle 3 roadmap (topics 41-80, same 40 concepts but "spot the bug"/"predict exact output" style only) added below, verified live against installed pandas 3.0.5 / numpy 2.5.3

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

## Roadmap — Cycle 3: same 40 concepts, harder style only (topics 41-80 map 1:1 onto Cycle 1 + Cycle 2's topics 1-40 above)

**Style rule for all of Cycle 3:** every question is "spot the bug in this snippet" or "predict the exact output of this code" — never "which command does X" or a bare definitional question. Reuse the same concepts with gnarlier, more realistic code (interactions between methods, real edge cases) rather than new topics, and never reuse a Cycle 1/2 question's exact scenario verbatim.

41. NumPy array creation & dtypes (revisits Topic 1)
42. NumPy indexing & slicing (revisits Topic 2)
43. NumPy vectorized ops & broadcasting (revisits Topic 3)
44. NumPy aggregations (revisits Topic 4)
45. NumPy boolean masking & `np.where` (revisits Topic 5)
46. Pandas Series: creation, index, basic ops (revisits Topic 6)
47. Pandas DataFrame creation from dict/list/np.array (revisits Topic 7)
48. Selection with `.loc` vs `.iloc` (revisits Topic 8)
49. Boolean filtering on a DataFrame (revisits Topic 9)
50. Adding/dropping columns & rows (revisits Topic 10)
51. Handling missing data (revisits Topic 11)
52. Sorting & ranking (revisits Topic 12)
53. GroupBy basics (revisits Topic 13)
54. GroupBy multiple keys & aggregations (revisits Topic 14)
55. Merge/join/concat (revisits Topic 15)
56. `apply`/`map`/`applymap` (revisits Topic 16)
57. String methods via `.str` (revisits Topic 17)
58. Datetime handling (revisits Topic 18)
59. Pivot tables & `pd.crosstab` (revisits Topic 19)
60. Reshaping: `melt`/`pivot`/`stack`/`unstack` (revisits Topic 20)
61. MultiIndex basics (revisits Topic 21)
62. Window functions (revisits Topic 22)
63. Categorical dtype (revisits Topic 23)
64. Combining NumPy + pandas (revisits Topic 24)
65. Performance: vectorization vs `.apply()` vs `.iterrows()` (revisits Topic 25)
66. Multi-step chained operations (revisits Topic 26)
67. `pivot_table` with custom `aggfunc` (revisits Topic 27)
68. Advanced boolean indexing `.isin()`/`~`/`.query()` (revisits Topic 28)
69. Merge mismatched keys/`indicator=True`/`validate=` (revisits Topic 29)
70. `groupby().transform()` vs `.agg()` vs `.apply()` (revisits Topic 30)
71. Duplicate data handling (revisits Topic 31)
72. Memory/dtype optimization (revisits Topic 32)
73. NumPy broadcasting edge cases (revisits Topic 33)
74. NumPy linear algebra basics (revisits Topic 34)
75. Named aggregations `pd.NamedAgg` (revisits Topic 35)
76. Time series resampling + rolling (revisits Topic 36)
77. JSON/nested structures via `json_normalize` (revisits Topic 37)
78. Method chaining style vs step-by-step (revisits Topic 38)
79. Common gotchas: views vs copies (revisits Topic 39)
80. Mixed review drawing on anything above, "spot the bug" style (revisits Topic 40)

After topic 80, start a **Cycle 4** — write new topics/entries here as that cycle is planned, don't just silently reuse Cycle 1/2/3 questions verbatim.
