# Keras (Tensorflow) Jupyter Notebook Stack

Docker image to work jupyter notebook and Keras


## Parent Docker image
https://github.com/tensorflow/tensorflow/tree/master/tensorflow/tools/docker


## What it Gives You

* Jupyter Notebook 4.3.x
* Python 3.x and Python 2.7.x environments
* matplotlib, numpy, scipy, scikit-learn, Pillow


## Basic Use

The following command starts a container with the Notebook server listening for HTTP connections on port 8888 with a randomly generated authentication token configured.

Run non-GPU container:
```
docker run -it --rm -p 8888:8888 keras-notebook
```

For GPU support install NVidia drivers (ideally latest) and nvidia-docker. Run using
```
$ nvidia-docker run -it -p 8888:8888 keras-notebook:latest-gpu
```

Take note of the authentication token included in the notebook startup log messages. Include it in the URL you visit to access the Notebook server or enter it in the Notebook login form.

```
docker run -it --rm -v $(pwd):/notebooks -p 8888:8888 tf-notebook
```

Uses the current directory and mounts it to /notebooks within the container.
