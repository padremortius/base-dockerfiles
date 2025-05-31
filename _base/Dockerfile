ARG PLATFORM="linux/arm64"

FROM --platform=${PLATFORM} registry.altlinux.org/alt/alt:p10

ARG VER
ARG BUILD_TIME

LABEL \
    OS="Alt Linux p10" \
    COMPANY="Company Name" \
    VERSION=$VER \
    MAINTAINER="padremortius" \
    org.opencontainers.image.description="Base image for Company Name" \
    org.opencontainers.image.created=${BUILD_TIME}

COPY certs/*.crt /etc/pki/ca-trust/source/anchors/

COPY apt_repo/alt.list /etc/apt/sources.list.d/

RUN apt-get update && apt-get dist-upgrade -y && \
    apt-get install -y curl jq && \
    update-ca-trust && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
