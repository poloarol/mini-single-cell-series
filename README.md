# Mini single-cell Series

This repository contains a hands-on tutorial for quality control of single-cell data. 
The first notebook, **Approaching Quality Control on MERFISH**, uses blank probes to 
identify cells with high background signal anddemonstrates how to visualize that signal alongside common cell-level QC
metrics.

## Getting started

The notebook uses Python with Jupyter and the following packages: `anndata`,
`matplotlib`, `numpy`, `pandas`, `scanpy`, `seaborn`, `squidpy`, and
`watermark`.

For example, in VS Code:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

## Repository contents

- [`01_quality_control.ipynb`](./01_quality_control.ipynb) — MERFISH quality
  control walkthrough.

This is a guide to model background noise using MERFISH data.

The walkthrough calculates standard cell-level metrics, including total
counts, detected features, and volume, then calculates blank-probe counts and
their percentage of total counts. It uses histograms, violin plots, and spatial
plots to explore these metrics.

For the bundled dataset, the notebook uses the 95th percentile of
`blank_counts` as a threshold. Cells with counts strictly greater than this
threshold are labeled **Above**; the rest are labeled **Below**. These labels
are visualized spatially, and the above-threshold cells are copied into a
separate object for inspection.
