# Week 2 datasets

The Week 2 notebooks load these files through the `data_path()` helper: from this folder if you have a local copy of the repository, otherwise directly from GitHub (e.g. in Colab).

| File | Used in | Contents |
| --- | --- | --- |
| `lancaster_quay_tidal.csv` | `week2_fitting.ipynb` | River Lune water level at Lancaster Quay (the Week 1 extract) |
| `graduate_earnings.csv` | `week2_fitting.ipynb` (optional extension) | Median UK salaries, 2007–2020 |

## `lancaster_quay_tidal.csv`

An identical copy of the Week 1 file, so each week's folder is self-contained. Source, dates, attribution and how to refresh it: see `workshops/week1/datasets/README.md`. If the Week 1 file is ever refreshed, replace this copy too, and update the numbers quoted in the Week 2 solutions.

## `graduate_earnings.csv`

- **Source:** carried over from PHYS465 (Week 11). Median salaries are from the UK government's graduate labour market statistics.
- **Columns:** `year`, `gender` (`all`, `male`, `female`), `graduate_type` (`graduate`, `non-graduate`, `postgraduate`), `income` (median salary, £, nominal), `income_err` (uncertainty, £).
- 126 rows: 14 years × 3 genders × 3 graduate types.
