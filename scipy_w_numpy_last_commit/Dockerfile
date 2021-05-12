FROM python:rc-buster

RUN apt-get update && apt-get install -y git

RUN apt-get install -y libatlas-base-dev liblapack-dev gfortran libgmp-dev libmpfr-dev libsuitesparse-dev ccache libmpc-dev g++ libboost-all-dev

RUN pip install --user git+https://github.com/numpy/numpy.git \
    && python3.10 -m pip install --user setuptools wheel cython pytest pybind11 pytest-xdist pythran

RUN git clone https://github.com/scipy/scipy.git && cd scipy && pip install -e .

WORKDIR scipy

RUN pip install -r mypy_requirements.txt && python3.10 -u runtests.py --mypy 
