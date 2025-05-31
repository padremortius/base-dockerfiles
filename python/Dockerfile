ARG BASE_IMAGE='devops-altlinux:p10-1.0.0'
ARG PLATFORM="linux/arm64"

FROM --platform=${PLATFORM} ${BASE_IMAGE}

ARG BUILD_TIME
ARG VER

LABEL \
    org.company_name.builder="Pip" \
    org.company_name.compiler="Python" \
    org.opencontainers.image.created=${BUILD_TIME} \
    VERSION=${VER}

RUN apt-get update && \
    apt-get install -y python3-module-pip && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
