# Follow the directions in the README to build and run the Docker container

FROM ubuntu:bionic

WORKDIR /workspace

RUN dpkg --add-architecture i386 \
    && apt-get update -q \
    && apt-get install -y --no-install-recommends \
        g++ \
        make \
        openssl \
        libssl-dev \
        libssl1.0.0 \
        git \
        ca-certificates \
    && update-ca-certificates \
    && git clone https://github.com/Xilinx/bootgen -b 2020.2 /bootgen \
    && make -C /bootgen \
    && mkdir /bootgen/bin \
    && cp /bootgen/bootgen /bootgen/bin

ARG USER=bootgen_builder

RUN useradd -ms /bin/bash $USER \
            && usermod -aG sudo $USER

USER $USER

ENV PATH="/bootgen/bin:${PATH}"
