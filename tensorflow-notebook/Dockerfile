
FROM jupyter/tensorflow-notebook

MAINTAINER Thierry Musy <thierry.musy@gmail.com>

USER root
# Do root stuff
RUN conda install --quiet --yes 'bcolz=1.0.0'
RUN conda install --quiet --yes -n python2 'bcolz=1.0.0'
RUN pip2 install keras

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_USER
