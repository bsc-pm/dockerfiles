FROM debian:stable-slim

RUN apt-get update && apt-get install -y \
    clang \
    gcc \
    g++ \
    gfortran \
    git \
    gcovr \
    python3 \
    autoconf \
    automake \
    libtool \
    make \
    libhwloc-dev \
    cmake \
    pkg-config \
    libglib2.0-dev \
    && rm -rf /var/lib/apt/lists/*
