ARG BASE_IMAGE='devops-altlinux:p10-1.0.0'
ARG PLATFORM="linux/arm64"

FROM --platform=${PLATFORM} ${BASE_IMAGE}

ARG GOLANG_VERSION
ARG BUILD_TIME
ARG VER

LABEL \
    org.company_name.compiler="Golang" \
    org.company_name.compiler.version="${GOLANG_VERSION}" \
    org.opencontainers.image.created=${BUILD_TIME} \
    VERSION=${VER}

RUN apt-get update && \
    apt-get install -y golang golang-tools && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
