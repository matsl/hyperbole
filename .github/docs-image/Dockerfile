FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

# install apt deps
COPY packages.txt .
RUN apt-get update && \
    xargs -a packages.txt apt-get install -y && \
    rm -rf /var/lib/apt/lists/*

# install pip deps
COPY pip.txt .
RUN pip3 install --break-system-packages -r pip.txt
