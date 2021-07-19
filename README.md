# Description

## Overview

Install current conda environment (`deepweather`) for my data-science-PhD in atmospheric physics with python language.

## Basic environment

This is how I make a basic and robust python installation for dealing with data-driven research in climate science. First we need to make sure to have access to ```conda-forge``` channel. This can be done following one out of two possibilities:

**1:** The following command adds the channel `conda-forge` to the top of the channel list, making it the highest priority:
```sh
$ conda config --add channels conda-forge
```
**2:** Conda also now has a command that adds the new channel `conda-forge` to the bottom of the channel list, making it the lowest priority:
```sh
$ conda config --append channels conda-forge
```
Then we can install basic python packages when creating an environment named `deepweather` with python 3.7 version:
```sh
$ conda create --name deepweather --verbose python=3.7 
```
After creating this environment, we activate it using its name ```deepweather```:
```sh
$ conda activate deepweather
```
A better option to further install python packages is to use [mamba](https://github.com/mamba-org/mamba), which is a reimplementation of the conda package manager in C++. 
```
$ (deepweather) conda install mamba --channel conda-forge
```
Now we install the remaining packages using mamba: 
```sh
$ (deepweather) mamba install --verbose \
    scipy pandas statsmodels \
    scikit-learn scikit-optimize xgboost \
    matplotlib seaborn plotly cartopy \
    patchelf jupyterlab ipywidgets qtconsole qtawesome tqdm \
    dask bottleneck numba cython pyarrow \ 
    xarray xesmf cmocean cftime nc-time-axis \
    pygrib cfgrib netCDF4 h5netcdf pseudonetcdf zarr \
    rioxarray salem regionmask \
    geopandas folium eofs rasterio pydot 
```
and then we can install some pip additional packages:
```sh
$ (deepweather) pip install \
    tensorflow=1.15 \
    ecmwf-api-client \
    nbresuse \
    seglearn \
    h2o \
    pymannkendall \
    dask_labextension
```

Let's see the purposes for some of the previously installed packages :

| Package page| Description |
|:---|:---|
| [plotly](https://plotly.com/python/getting-started/) | The plotly Python library is an interactive, open-source plotting library that supports over 40 unique chart types covering a wide range of statistical, financial, geographic, scientific, and 3-dimensional use-cases. |
| [dask](https://dask.org/) | Dask provides advanced parallelism for analytics, enabling performance at scale for the tools you love. |
| [bottleneck](https://github.com/pydata/bottleneck) | Bottleneck is a collection of fast, NaN-aware NumPy array functions written in C. |
| [numba](http://numba.pydata.org/) | Numba is an open source JIT compiler that translates a subset of Python and NumPy code into fast machine code. |
| [pyarrow](https://arrow.apache.org/) | A cross-language development platform for in-memory analytics. |
| [scikit-optimize](https://scikit-optimize.github.io/stable/index.html) | Sequential model-based optimization in Python. |
| [xarray](http://xarray.pydata.org/en/stable/) | xarray (formerly xray) is an open source project and Python package that makes working with labelled multi-dimensional arrays simple, efficient, and fun! |
| [geopandas](https://geopandas.org/) | GeoPandas is an open source project to make working with geospatial data in python easier. |
| [cartopy](https://scitools.org.uk/cartopy/docs/latest/) | Cartopy is a Python package designed for geospatial data processing in order to produce maps and other geospatial data analyses. |
| [folium](https://python-visualization.github.io/folium/) | folium builds on the data wrangling strengths of the Python ecosystem and the mapping strengths of the leaflet.js library. Manipulate your data in Python, then visualize it in on a Leaflet map via folium. |
| [eofs](https://ajdawson.github.io/eofs/latest/) | eofs is a Python package for EOFs (empirical orthogonal functions) analysis of spatial-temporal data. |
| [pygrib](https://github.com/jswhit/pygrib) | Python module for reading/writing GRIB files. |
| [cfgrib](https://github.com/ecmwf/cfgrib) | Python interface to map GRIB files to the NetCDF Common Data Model following the CF Convention using ecCodes. |
| [netCDF4](https://github.com/Unidata/netcdf4-python) | netcdf4-python is a Python interface to the netCDF C library. |
| [h5netcdf](https://github.com/shoyer/h5netcdf) | A Python interface for the netCDF4 file-format that reads and writes local or remote HDF5 files directly via h5py or h5pyd, without relying on the Unidata netCDF library. |
| [pseudonetcdf](https://github.com/barronh/pseudonetcdf) | PseudoNetCDF provides read, plot, and sometimes write capabilities for atmospheric science data formats. |
| [zarr](https://zarr.readthedocs.io/en/stable/) | Zarr is a Python package providing an implementation of chunked, compressed, N-dimensional arrays. |
| [rasterio](https://rasterio.readthedocs.io/en/latest/) | Geographic information systems use GeoTIFF and other formats to organize and store gridded raster datasets such as satellite imagery and terrain models. Rasterio reads and writes these formats and provides a Python API based on Numpy N-dimensional arrays and GeoJSON. |
| [cmocean](https://github.com/matplotlib/cmocean) | Beautiful colormaps for oceanography. |
| [pydot](https://github.com/pydot/pydot) | Python interface to Graphviz's Dot. |
| [xesmf](https://xesmf.readthedocs.io/en/latest/) | Universal Regridder for Geospatial Data. |
| [cftime](https://github.com/unidata/cftime) | Time-handling functionality from netcdf4-python. |
| [rioxarray](https://github.com/corteva/rioxarray) | Geospatial xarray extension powered by rasterio. |
| [salem](https://salem.readthedocs.io/en/stable/index.html) | Salem is a small library to do geoscientific data processing and plotting. It extends xarray to add geolocalised subsetting, masking, and plotting operations to xarray’s DataArray and DataSet structures. |
| [regionmask](https://regionmask.readthedocs.io/en/stable/index.html) | Create masks of geographical regions. |
| [ecmwf-api-client](https://github.com/ecmwf/ecmwf-api-client) | Python API to access ECMWF archive. |
| [nbresuse](https://github.com/yuvipanda/nbresuse) | NB Resource Usage (NBResuse) is a small extension for Jupyter Notebooks that displays an indication of how much resources your current notebook server and its children (kernels, terminals, etc) are using. This is displayed in the main toolbar in the notebook itself, refreshing every 5s. |
| [seglearn](https://github.com/dmbee/seglearn) | Seglearn is a python package for machine learning time series or sequences. |
| [h2o](https://docs.h2o.ai/h2o/latest-stable/h2o-py/docs/intro.html#what-is-h2o) | This Python module provides access to the H2O JVM, as well as its extensions, objects, machine-learning algorithms, and modeling support capabilities, such as basic munging and feature generation. |
| [pymannkendall](https://github.com/mmhs013/pymannkendall) | pyMannkendal is a pure Python implementation of non-parametric Mann-Kendall trend analysis, which bring together almost all types of Mann-Kendall Test. |

See more in [Managing conda environments](https://conda.io/docs/user-guide/tasks/manage-environments.html#managing-environments).

## Jupyter lab extensions  

In order to install JupyterLab extensions, you need to have [node.js](https://nodejs.org/en/) installed. Follow [this Ubuntu 18.04 tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04-pt) using PPA method to have more updated versions than the ones found in official Ubuntu repositories. After obtaining an updated version of nodejs, then we can install some useful extensions directly from the `Extension Manager` tab when we enable it. Also, we can explicitly install these extensions from command line, as exemplified below:

- [jupyterlab-toc](https://github.com/jupyterlab/jupyterlab-toc): A Table of Contents extension for JupyterLab. This auto-generates a table of contents in the left area when you have a notebook or markdown document open. The entries are clickable, and scroll the document to the heading in question.
    - `$ (deepweather) jupyter labextension install @jupyterlab/toc`

- [jupyterlab-spellchecker](https://github.com/ijmbarr/jupyterlab_spellchecker): The JupyterLab extension is based on the spellchecker Jupyter Notebook extension and relies on Typo.js for the actual spell checking. Spellchecker suggestions are available from the context menu.
    - `$ (deepweather) jupyter labextension install @ijmbarr/jupyterlab_spellchecker` 

- [dask-labextension](https://github.com/dask/dask-labextension): This package provides a JupyterLab extension to manage Dask clusters, as well as embed Dask's dashboard plots directly into JupyterLab panes.
    - `$ (deepweather) jupyter labextension install dask-labextension`
    - `$ (deepweather) jupyter serverextension enable dask_labextension`

## JupyterLab on cluster node (HPC)

To run JupyterLab on a specific computing node, for instance `nxxx` in some `cluster` resource, first we need to login in this node by ssh and then activate our previously installed conda `environment`. Now we start a JupyterLab instance and forward traffic to a specific port, `8888` in the following snippet:
```sh
(environment) username@nxxx:~> jupyter-lab --port 8888 --no-browser
```
After that, we go to another local terminal and type the following command:
```sh
$ ssh -t -t username@cluster -L 8890:localhost:1234 ssh nxxx -L 1234:localhost:8888
```
Let's understand the above commands:

- The first ssh starts a tunnel between our local machine and head node of `cluster`.
- `-t -t` forces a tty on head node. This is required to tunnel data back to head node from node `nxxx`.
- `-L 8890:localhost:1234` directs ssh to tunnel traffic from port `8890` on local machine to port `1234` on head node of remote server (the general form is `[local port]:[remote ip]:[remote port]`).
- The second ssh starts a tunnel between head node and `nxxx` node.
- `-L 1234:localhost:8888` directes ssh to tunnel traffic from port `1234` on head node to port `8888` of `nxxx` computing node.

Finally, we can head on to our browser at `localhost:8890` where our JupyterLab instance resides. See more on the following tutorials:

- [Remote Jupyter Lab: how to utilize Jupyter Lab to its fullest on a remote server](https://medium.com/spencerweekly/remote-jupyter-lab-how-to-utilize-jupyter-lab-to-its-fullest-on-a-remote-server-2a359159d2f6).
- [Running Jupyter Lab on HPC](https://www.sichong.site/2020/02/07/running-jupyter-lab-on-hpc/).