FROM python:rc-buster

RUN apt-get update && \
    apt install -y git curl libatlas-base-dev liblapack-dev gfortran libgmp-dev libmpfr-dev libsuitesparse-dev ccache libmpc-dev g++

RUN pip install --user git+https://github.com/numpy/numpy.git && \
    pip install --user setuptools wheel cython pytest pybind11 pytest-xdist pythran sphinx pydata-sphinx-theme sphinx-panels matplotlib mypy

# Install Scipy
RUN git clone https://github.com/scipy/scipy.git && cd scipy && pip install -e .
