FROM ubuntu:22.04

ENV \
     SHELL="/bin/bash" \
     DEBIAN_FRONTEND="noninteractive"

RUN sed -i s/archive.ubuntu.com/mirrors.aliyun.com/g /etc/apt/sources.list && \
    sed -i s/security.ubuntu.com/mirrors.aliyun.com/g /etc/apt/sources.list && \
    apt update && \
    apt install -y curl git gnupg jq lsb-release sudo unzip wget zip

RUN apt install -y \
    cmake \
    valgrind \
    libssl-dev \
    zlib1g-dev \
    libboost-test-dev \
    libboost-filesystem-dev \
    libboost-iostreams-dev \
    libboost-program-options-dev \
    libboost-system-dev \
    libboost-thread-dev \
    libboost-date-time-dev \
    build-essential

SHELL ["/bin/bash", "-c"]

RUN useradd -m -s /bin/bash vscode && echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

WORKDIR /workspace