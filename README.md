# an example of using dask with napari

*This notebook was prepared for the life science workshop at the 2021 Dask
Summit. It is an interactive version of the post
https://napari.org/tutorials/applications/dask.html (deconvolution has been
removed for ease of environment setup)*

## Problem

**Light sheet microscopy** is an emerging light microscopy technique that often
generates large multidimensional datasets (10s - 1,000s of GB with 4+
dimensions).

#### out-of-core
It's a pretty standard "out-of-core" problem: simply visualizing data can be
challenging without specialized hardware.


#### storage burden vs convenience
Preprocessing is sometimes required to visualize or analyze data.

Thus, a tradeoff has to be made between ease of visualizing datasets (by storing
pre-processing data along with raw data) and minimizing data-storage burden.

## Lazy IO & processing facilitates visualization, minimizes storage.

The combination of napari (a multi-dimensional python viewer), dask (scalable,
delayed processing with standard APIs), and some rapid GPU-based processing,
provides a workflow that allows us to store the bare minimum raw data on disk,
while still being able to review the "expanded"/processed data at arbitrary
points in a large experiment on demand.

## Running this notebook

```
conda env create -f environment.yml
conda activate napari-dask

jupyter-lab napari_dask.ipynb
```
