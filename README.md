# Description

## Overview

Install my current conda python environment for data science in general and my phd studies.

## Basic environment

This is how I make a basic and robust python installation for general purposes in data science (__please note that, due to my background, you can see a lot of packages for climate data analysis within my installation below__). First we need to make sure to have access to ```conda-forge``` channel. This can be done following one out of two possibilities:

**1:** The following command adds the channel ```conda-forge``` to the top of the channel list, making it the highest priority:

```sh
$ conda config --add channels conda-forge
```

**2:** Conda also now has a command that adds the new channel ```conda-forge``` to the bottom of the channel list, making it the lowest priority:

```sh
$ conda config --append channels conda-forge
```

Then we can install all the basic packages when creating the environment named ```my_env``` with python 3.6 version:

```sh
$ conda create --name my_env --verbose python=3.6 xarray jupyterlab statsmodels cartopy \
cmocean esmf iris progressbar2 pygrib scikit-learn basemap matplotlib qtconsole qtawesome \
seaborn pandas spyder metpy cfgrib scipy sympy networkx jpype1 cython cftime rasterio zarr \
pynio h5netcdf bottleneck netCDF4 pseudonetcdf aospy esmpy eofs numba python-cdo keras \
tensorflow kaggle jedi geopandas ipywidgets nc-time-axis pydot pyarrow
```

After creating this environment, we activate it using his name ```my_env```:

```sh
$ conda activate my_env
```
and then we can install additional packages with pip:

```sh
$ pip install cmipdata ecmwf-api-client pysplit sklearn-xarray xesmf mvd pylatex \
jupyterlab_latex jupyterlab-git nbresuse gym atari-py seglearn h2o pymannkendall
```

Let's see the purposes for some of the previously installed packages :

| Package | Description |
|:---|:---|
| esmf | The Earth System Modeling Framework (ESMF) is software for building and coupling weather, climate, and related models. |
| pygrib | Python module for reading/writing GRIB files. |
| MetPy | Collection of tools for reading, visualizing and performing calculations with weather data. |
| cfgrib | Python interface to map GRIB files to the NetCDF Common Data Model following the CF Convention using ecCodes. |
| JPype1 | A Python to Java bridge. |
| aospy | Automated gridded climate data analysis and management. |
| jedi | An autocompletion tool for Python that can be used for text editors. | 
| cmipdata | Processing tools for large ensembles of CMIP type netcdf data. |
| ecmwf-api-client | Python client for ECMWF web services API. |
| PySPLIT | HYSPLIT trajectory analysis, automation, and visualization. |
| sklearn-xarray | xarray integration with sklearn. |
| xesmf | Universal Regridder for Geospatial Data. |
| mvd | Terminal Markdown Viewer. |
| nbresuse | Simple Jupyter extension to show how much resources (RAM) your notebook is using. |
| nc-time-axis | Support for cftime axis in matplotlib. |
| gym | The OpenAI Gym: A toolkit for developing and comparing your reinforcement learning agents. |
| atari-py | Python bindings to Atari games. |
| pydot | Python interface to Graphviz's Dot. |
| seglearn | A template for scikit-learn compatible packages (time series / sequences data). |
| h2o | H2O, Fast Scalable Machine Learning, for python. | 
| pymannkendall | A python package for non parametric Mann Kendall family of trend tests. |

## Extensions for jupyter-lab

Currently I am trying to use some extensions for improving jupyter-lab experience:

```sh
$ jupyter labextension list
JupyterLab v1.0.5
Known labextensions:
   app dir: /home/alex/anaconda3/envs/machine36/share/jupyter/lab
        @jupyter-widgets/jupyterlab-manager v1.0.2  enabled  OK
        @jupyterlab/git v0.8.0  enabled  OK
        @jupyterlab/github v1.0.1  enabled  OK
        @jupyterlab/latex v1.0.0  enabled  OK
        @jupyterlab/plotly-extension v1.0.0  enabled  OK
        jupyterlab-drawio v0.6.0  enabled  OK
        jupyterlab_bokeh v1.0.0  enabled  OK
        nbdime-jupyterlab v1.0.0  enabled  OK
```

## Creating an environment from an environment.yml file

```sh
$ conda env create -f environment.yml
```

The first line of the ```yml``` file sets the new environment’s name. 

## Building identical conda environments

An explicit spec file (txt extension) is not usually cross platform, and therefore has a comment at the top such as ```platform: osx-64``` showing the platform where it was created. This platform is the one where this spec file is known to work. On other platforms, the packages specified might not be available or dependencies might be missing for some of the key packages already in the spec.

To use the spec file to create an identical environment on the same machine or another machine:

```sh
$ conda create --name myenv --file spec-file.txt
```

To use the spec file to install its listed packages into an existing environment:

```sh
$ conda install --name myenv --file spec-file.txt
```

Conda does not check architecture or dependencies when installing from a spec file. To ensure that the packages work correctly, make sure that the file was created from a working environment, and use it on the same architecture, operating system and platform, such as linux-64 or osx-64.

See more in [Managing conda environments](https://conda.io/docs/user-guide/tasks/manage-environments.html#managing-environments).