# Dockerfile
FROM bscpm/ompss:latest

RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        libopenmpi-dev \
        openmpi-bin \
        ssh \
    && rm -rf /var/lib/apt/lists/*

CMD ["bash"]
