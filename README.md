# Description

## Overview

Install current conda environment for my data-science-PhD in atmospheric physics with python language.

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

Then we can install all the basic packages when creating the environment named `my_env` with python 3.6 version:
```sh
$ conda create --name my_env --verbose python=3.6 scipy pandas matplotlib seaborn jupyterlab spyder ipywidgets \
qtconsole qtawesome progressbar2 statsmodels bottleneck numba cython pyarrow scikit-learn tensorflow keras \
xarray geopandas cartopy folium eofs pygrib cfgrib netCDF4 h5netcdf pseudonetcdf zarr rasterio cmocean pydot \
xesmf cftime nc-time-axis
```
After creating this environment, we activate it using his name ```my_env```:
```sh
$ conda activate my_env
```
and then we can install additional packages with pip:
```sh
$ (my_env) pip install ecmwf-api-client nbresuse seglearn h2o pymannkendall
```

Let's see the purposes for some of the previously installed packages :

| Package page| Description |
|:---|:---|
| [bottleneck](https://github.com/pydata/bottleneck) | Bottleneck is a collection of fast, NaN-aware NumPy array functions written in C. |
| [numba](http://numba.pydata.org/) | Numba is an open source JIT compiler that translates a subset of Python and NumPy code into fast machine code. |
| [pyarrow](https://arrow.apache.org/) | A cross-language development platform for in-memory analytics. |
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
| [ecmwf-api-client](https://github.com/ecmwf/ecmwf-api-client) | Python API to access ECMWF archive. |
| [nbresuse](https://github.com/yuvipanda/nbresuse) | NB Resource Usage (NBResuse) is a small extension for Jupyter Notebooks that displays an indication of how much resources your current notebook server and its children (kernels, terminals, etc) are using. This is displayed in the main toolbar in the notebook itself, refreshing every 5s. |
| [seglearn](https://github.com/dmbee/seglearn) | Seglearn is a python package for machine learning time series or sequences. |
| [h2o](https://docs.h2o.ai/h2o/latest-stable/h2o-py/docs/intro.html#what-is-h2o) | This Python module provides access to the H2O JVM, as well as its extensions, objects, machine-learning algorithms, and modeling support capabilities, such as basic munging and feature generation. |
| [pymannkendall](https://github.com/mmhs013/pymannkendall) | pyMannkendal is a pure Python implementation of non-parametric Mann-Kendall trend analysis, which bring together almost all types of Mann-Kendall Test. |

See more in [Managing conda environments](https://conda.io/docs/user-guide/tasks/manage-environments.html#managing-environments).

## Jupyter lab extensions  

In order to install JupyterLab extensions, you need to have [node.js](https://nodejs.org/en/) installed. Follow [this Ubuntu 18.04 tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04-pt) using PPA method in order to have more updated versions than the ones found in official Ubuntu repositories. After obtaining an updated version of nodejs, then we can install some useful extensions:

- [jupyterlab-toc](https://github.com/jupyterlab/jupyterlab-toc): A Table of Contents extension for JupyterLab. This auto-generates a table of contents in the left area when you have a notebook or markdown document open. The entries are clickable, and scroll the document to the heading in question.
    - `$ (my_env) jupyter labextension install @jupyterlab/toc`