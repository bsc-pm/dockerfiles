FROM debian:stable-slim

RUN apt-get update && apt-get install -y \
    gcc \
    g++ \
    gfortran \
    git \
    gcovr \
    python2.7 \
    autoconf \
    automake \
    libtool \
    make \
    libhwloc-dev \
    && rm -rf /var/lib/apt/lists/*
