# Follow the directions in the README to build and run the Docker container

FROM alpine:3.15

WORKDIR /workspace

RUN apk update && \
    apk upgrade && \
    apk add xilinx_bootgen=2021.1-r1

ARG USER=bootgen_builder

RUN addgroup -S $USER && adduser -S $USER -G $USER

USER $USER