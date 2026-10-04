# Week 1 datasets

The Week 1 notebooks load these files through a small `data_path()` helper: from this folder if you have a local copy of the repository, otherwise directly from GitHub (e.g. in Colab).

| File | Used in | Contents |
| --- | --- | --- |
| `lancaster_quay_tidal.csv` | `week1_tidal_hook.ipynb`, `week1_setup.ipynb` | River Lune water level at Lancaster Quay |
| `pandas_practice_dataset.csv` | `week1_revision.ipynb` | A small, deliberately messy table of exercise sessions |
| `isotope_masses.csv` | `week1_foundations.ipynb` | Measured atomic masses of eight isotopes |

## `lancaster_quay_tidal.csv`

- **Source:** Environment Agency real-time flood-monitoring API, station `724735` (Lancaster Quay, River Lune), measure `724735-level-stage-i-15_min-m`.
- **Extract:** 766 readings every 15 minutes, 24 Sep 2026 18:00 to 2 Oct 2026 17:30 (UTC). There is one 30-minute gap.
- **Columns:** `time` (UTC, ISO 8601), `level_m` (water level, metres).
- **Known features:** about half the readings sit on a low-water plateau at ~2.22 m; the peaks are ~12.3 hours apart (the M2 tide).
- **Why a fixed extract:** every student sees the same numbers, results don't change from year to year, and the notebooks work without the live API.
- **Attribution:** this uses Environment Agency flood and river level data from the real-time data API (Beta), available under the Open Government Licence.
- **Background:** the tidal case study in Rowland Adams, J., Newman, J. & Stefanovska, A. (2023), *Distinguishing between deterministic oscillations and noise*, Eur. Phys. J. Spec. Top. 232, 3435–3457 (their Fig. 4) uses this gauge. Their archived series (16–25 Feb 2022, [doi:10.17635/lancaster/researchdata/609](https://doi.org/10.17635/lancaster/researchdata/609)) is part of a 16.3 GB data-and-code bundle, which is why it isn't used here.

**To refresh the extract** (e.g. for a new year, or a longer record), run this anywhere with normal internet access, then replace the file in this folder and push:

```python
import requests
import pandas as pd
from datetime import datetime, timedelta, timezone

hours = 192   # 8 days
since = (datetime.now(timezone.utc) - timedelta(hours=hours)).strftime("%Y-%m-%dT%H:%M:%SZ")
url = ("https://environment.data.gov.uk/flood-monitoring/id/measures/"
       "724735-level-stage-i-15_min-m/readings")
resp = requests.get(url, params={"since": since, "_limit": 10000}, timeout=20)
resp.raise_for_status()

df = pd.DataFrame(resp.json()["items"])[["dateTime", "value"]]
df["dateTime"] = pd.to_datetime(df["dateTime"])
df = df.rename(columns={"dateTime": "time", "value": "level_m"}).sort_values("time")
df.to_csv("lancaster_quay_tidal.csv", index=False)
print(len(df), "readings saved")
```

The live API only keeps recent readings, so a longer historical record needs the Environment Agency's archive service instead. If the dates change, update the date range quoted in `week1_tidal_hook.ipynb` (loading code) and the numbers quoted in its Section 3 text.

## `pandas_practice_dataset.csv`

- **Source:** carried over from PHYS465. It is the "dirty data" example from the W3Schools pandas data-cleaning tutorial.
- **Columns:** `Duration` (minutes), `Date`, `Pulse`, `Maxpulse` (beats per minute), `Calories`.
- **Deliberate problems:** dates wrapped in quote marks, one date written as `20201226`, one missing date, a `Duration` of 450 (almost certainly 45), a duplicated row (12 Dec), one row with `Maxpulse` below `Pulse`, and two missing `Calories` values. These are what make revision Exercise 3 need cleaning first. **Don't tidy the file.**

## `isotope_masses.csv`

- **Source:** NIST, *Atomic Weights and Isotopic Compositions*.
- **Columns:** `isotope`, `Z`, `N`, `A`, `atomic_mass_u` (atomic mass in unified atomic mass units), `source`.
- **Isotopes:** H-2, He-4, C-12, O-16, Fe-56, Pb-208, U-235, U-238.
- The hydrogen-1 and neutron masses and the u → MeV conversion used in the binding-energy exercise are CODATA values, set in the notebook itself.
