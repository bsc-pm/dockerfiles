FROM ubuntu:24.10
ARG DLB_VERSION="git"

USER root
SHELL ["/bin/bash", "-c"]
ENV DEBIAN_FRONTEND=noninteractive

USER root
# Installing necessary dependencies
RUN apt-get -qq update && \
    apt-get -qq -y install \
        # basics
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
        unzip

USER ubuntu

RUN mkdir -p /home/ubuntu/dlb && \
    cd /home/ubuntu/dlb && \
    if [ "${DLB_VERSION}" = "git" ]; then \
        wget https://github.com/bsc-pm/dlb/archive/refs/heads/main.zip && \
        unzip main.zip && \
        cd dlb-main ;\
    else \
        wget https://github.com/bsc-pm/dlb/archive/refs/tags/v${DLB_VERSION}.tar.gz && \
        tar -xf v${DLB_VERSION}.tar.gz && \
        cd dlb-${DLB_VERSION} ; \
    fi && \
    ./bootstrap && \
    ./configure --with-mpi --prefix=/home/ubuntu/dlb --with-papi && \
    make -j $(($(nproc)-1)) && make install

ENV PATH="${PATH}:/home/ubuntu/dlb/bin"
ENV DLB_HOME="/home/ubuntu/dlb"

WORKDIR /home/ubuntu
