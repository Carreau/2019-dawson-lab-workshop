# Jupyter/JupyterLab workshop

This repository contain material and instructions to follow the "Getting started with JupyterLab"


# Installation

Please read the following section and install the required software ahead of
time. We may ask you to update versions of the software more closely to the
tutorial date.

Please do not rely on cloud hosting to follow this tutorial, as the network
connection may be unreliable. If possible, come to the tutorial with a computer
where you have administrative privileges.

For this tutorial, we are standardizing on a conda-based python distribution
(miniconda or Anaconda). We may not be able to help with installation issues if
you are using a different python distribution.

## Software installation

1. Install either the full [anaconda
   distribution](https://www.anaconda.com/download/) (very large, includes lots
   of conda packages by default) or
   [miniconda](https://conda.io/miniconda.html) (much smaller, with only
   essential packages by default, but any conda package can be installed).

2. To get the tutorial materials, clone this repository.

    ```
    git clone https://github.com/Carreau/2019-dawson-lab-workshop
    ```

    To update the materials:
    ```
    cd 2019-dawson-lab-workshop $
```


## Starting JupyterLab

Enter the following command in a new terminal window to start JupyterLab.

```
$ jupyter lab
```

## Removing environment

You can delete the environment by using the following in a terminal prompt.

```
conda env remove --name dawson-workshop --yes
```

This will **not** delete any data, but only the conda environement named `dawson-workshop` .

# Optional packages

We are demonstrating a few packages not installed in the above lists. These are
optional, and not required for the exercises in this tutorial.

To install these, first activate the tutorial environment:

```
conda activate dawson-workshop
```

Then install the python packages:
```
conda install -c conda-forge --override-channels --yes ipyleaflet ipympl
pip install sidecar
```

and install the JupyterLab extensions:
```
jupyter labextension install jupyterlab-toc jupyter-leaflet @jupyter-widgets/jupyterlab-sidecar jupyterlab-drawio
```

# Troubleshooting

If you experience an out-of-memory error, you can increase the memory available:
```
NODE_OPTIONS=--max_old_space_size=4096 jupyter lab build
```
or
```
NODE_OPTIONS=--max_old_space_size=4096 jupyter labextension install ...
```
This increases the available memory for the build process to 4Gb.
