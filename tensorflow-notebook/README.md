# Tensorflow Jupyter Notebook Stack

Docker image for working in the notebook and Tensorflow

## What it Gives You

All from https://github.com/jupyter/docker-stacks/tree/master/tensorflow-notebook, which is:
* Jupyter Notebook 4.3.x
* Conda Python 3.x and Python 2.7.x environments
* pandas, matplotlib, scipy, seaborn, scikit-learn, scikit-image, sympy, cython, patsy, statsmodel, cloudpickle, dill, numba, bokeh, vincent, beautifulsoup, xlrd pre-installed
* Unprivileged user jovyan (uid=1000, configurable, see options) in group users (gid=100) with ownership over /home/jovyan and /opt/conda
* tini as the container entrypoint and start-notebook.sh as the default command
* A start-singleuser.sh script useful for running a single-user instance of the Notebook server, as required by JupyterHub
* A start.sh script useful for running alternative commands in the container (e.g. ipython, jupyter kernelgateway, jupyter lab)
* Options for HTTPS, password auth, and passwordless sudo
* Tensorflow for Python 2.7 and 3.5 (without GPU support)


## Basic Use

The following command starts a container with the Notebook server listening for HTTP connections on port 8888 with a randomly generated authentication token configured.

```
docker run -it --rm -p 8888:8888 tf-notebook
```

Take note of the authentication token included in the notebook startup log messages. Include it in the URL you visit to access the Notebook server or enter it in the Notebook login form.

```
docker run -it --rm -v $(pwd):/home/jovyan/work -p 8888:8888 tf-notebook
```

Uses the current directory and mounts it to /home/jovyan/work within the container.
