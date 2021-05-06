FROM ubuntu:latest

RUN apt-get update && apt-get install -y software-properties-common curl\
    && apt-get update \
    && add-apt-repository ppa:deadsnakes/ppa \
    && apt-get update \
    && apt-get install -y --no-install-recommends python3.9-dev python3.9-distutils python3.9-venv

RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3.9 get-pip.py \
    && python3.9 -m pip install --upgrade pip setuptools

RUN apt-get install -y libatlas-base-dev liblapack-dev gfortran libgmp-dev libmpfr-dev libsuitesparse-dev ccache libmpc-dev g++

RUN python3.9 -m pip install --user -i https://pypi.anaconda.org/scipy-wheels-nightly/simple numpy \
    && python3.9 -m pip install --user setuptools wheel cython pytest pybind11 pytest-xdist pythran
