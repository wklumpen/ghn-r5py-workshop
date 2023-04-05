# GHN Spatial Analysis Workshop

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/wklumpen/ghn-r5py-workshop/HEAD)

![sponsors](img/sponsor_banner_backed.png)

This repository contains a series of workbooks and datasets that are useful for learning how to calculate your own transit access to opportunity measures and distributive equity measures using only open-source data and software.

These notebooks use [r5py](https://r5py.readthedocs.io/en/stable/), a Python-based wrapper for Conveyal's [R5](https://github.com/conveyal/r5) routing engine, which is very fast and has features that make it especially good for calculating transit travel time matrices.

There are also workbooks here that focus on calculating access to opportunity metrics as well as distributive equity metrics across population groups, in order to identify potentially systemic gaps in the provision of transit service.

This repository's analysis focuses on Calgary, Canada.

It is possible to run this analysis using a cloud-hosted Jupyter notebook service called Binder (click the "open in binder" icon above to do so), however running travel time matrices requires a decent amount of computational resources and will almost certainly be more robust if run locally. Please follow the installation instructions below to get it set up on your computer.

## Installation
There are may different ways to install both r5py and the other required tools on your computer. If you are familiar with environment management you can loosely follow this guide. If you are starting from scratch, here are the recommended steps:

### 1. Get the Code
You can get the code either by cloning this repository using Git, or by downloading a Zipped file of the code by going to Code -> Download ZIP on the main repository page. Extract this zipped folder somewhere on your computer.

### 2. Install Miniconda and Mamba

#### 2a: Install from Mambaforge
If you have not installed Python or Conda on your computer before, your best bet is to start with [Mambaforge](https://github.com/conda-forge/miniforge#mambaforge) (available for Windows/Linux/Mac).

Depending on how things have been installed, you may have to [add Conda to your PATH variable](https://stackoverflow.com/questions/44597662/conda-command-is-not-recognized-on-windows-10), and then run the command:

    conda init

Which will add `(base)` to the start of your terminal line.

#### 2b: Starting with an existing Conda distribution
If you're starting from another conda distribution, make sure you have `mamba` available on your system by installing it into the base environment (If you've used Mambaforge above you can skip this step):

    conda install -n base -c conda-forge mamba


### 3. Install Dependencies
Next you need to install the dependencies. To do this you will need to open a command prompt or terminal and navigate to the repository folder. To ensure you have the environment you need, you should install directly from the `local_install.yml` file located in the main repository folder:

    mamba create -n ghn -f local_install.yml

This will install a whole number of useful packages. You will need to confirm installation with `y` at some point. To check that your installation worked, you need to activate your environment:

    conda activate ghn

And then check packages are working with

    python
    >>> import r5py

This might take a little while if it's the first time you're importing as r5py needs to download a file. If you see no errors, you can exit the Python interpreter with `exit()` and you're good to go. 

### 4. Launch Jupyter Lab
To work with the notebooks and to follow along in the workshop launch JupyterLab with the command:

    python -m jupyter-lab

## Useful Resources
Much of the code and analysis in this repository comes directly from or is inspired by:

- The [r5py usage guide](https://r5py.readthedocs.io/en/stable/notebooks/basic-usage.html)
- The [Equity of Transport Futures](https://github.com/wklumpen/equity-transport-futures) code and guidebook

## Citing
If you end up using r5py in your work, please consider [citing it properly](https://github.com/r5py/r5py#citation)
