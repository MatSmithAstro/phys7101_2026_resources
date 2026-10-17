# Week 3 datasets

The Week 3 notebooks load these files through the `data_path()` helper: from this folder if you have a local copy of the repository, otherwise directly from GitHub (e.g. in Colab).

| File | Used in | Contents |
| --- | --- | --- |
| `co2_mm_mlo.csv` | `week3_interpolation.ipynb`, `week3_derivatives_integrals.ipynb` | Monthly mean atmospheric CO₂ at Mauna Loa, March 1958 – August 2026 |
| `lancaster_quay_tidal.csv` | `week3_derivatives_integrals.ipynb` (optional extension) | River Lune water level at Lancaster Quay (the Week 1 extract) |

## `co2_mm_mlo.csv`

- **Source:** NOAA Global Monitoring Laboratory, <https://gml.noaa.gov/ccgg/trends/>, file `co2_mm_mlo.csv` (created 5 September 2026), stored unchanged so that every student sees the same numbers.
- **Credit:** Dr. Xin Lan, NOAA/GML (gml.noaa.gov/ccgg/trends/) and Dr. Ralph Keeling, Scripps Institution of Oceanography (scrippsco2.ucsd.edu/).
- **Format:** comment lines starting `#` (read with `pd.read_csv(..., comment="#")`), then `year`, `month`, `decimal date`, `average` (ppm), `deseasonalized` (ppm), `ndays`, `sdev`, `unc`.
- **Missing values:** negative `ndays`, `sdev` and `unc` (−1, −9.99, −0.99) mark months with no daily statistics: all of March 1958 – April 1974 (Scripps data) and December 1975 (filled by NOAA). There are no gaps in `average`.
- December 2022 – July 2023 are from Maunakea, after the Mauna Loa eruption (see the file header).
- **To refresh:** download the file again from the link above. The numbers quoted in the Week 3 solutions use data up to August 2026, so rerun the solutions if you replace it.

## `lancaster_quay_tidal.csv`

An identical copy of the Week 1 file. Source, dates and attribution: see `workshops/week1/datasets/README.md`.
