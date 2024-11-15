FROM ubuntu:24.10
ARG DLB_VERSION="git"

SHELL ["/bin/bash", "-c"]
ENV DEBIAN_FRONTEND=noninteractive

# Installing necessary dependencies
RUN apt-get -qq update && \
    apt-get -qq -y install \
        build-essential \
        software-properties-common \
        cmake \
        curl \
        gfortran \
        papi-tools \
        libpapi-dev \
        libopenmpi-dev \
        openmpi-bin \
        openmpi-common \
        lsb-release \
        pkg-config \
        python3 \
        wget \
        libomp5-19 \
        unzip \
    && rm -rf /var/lib/apt/lists/*

RUN cd /usr/local/src && \
    if [ "${DLB_VERSION}" = "git" ]; then \
        wget https://github.com/bsc-pm/dlb/archive/refs/heads/main.zip && \
        unzip main.zip && \
        cd dlb-main ; \
    else \
        wget https://github.com/bsc-pm/dlb/archive/refs/tags/v${DLB_VERSION}.tar.gz && \
        tar -xf v${DLB_VERSION}.tar.gz && \
        cd dlb-${DLB_VERSION} ; \
    fi && \
    ./bootstrap && \
    ./configure --with-mpi --prefix=/usr/local --with-papi && \
    make -j $(($(nproc)-1)) && \
    make install

ENV DLB_HOME="/usr/local"
