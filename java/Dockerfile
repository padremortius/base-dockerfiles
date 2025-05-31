ARG BASE_IMAGE='devops-altlinux:p10-1.0.0'
ARG PLATFORM="linux/arm64"

FROM --platform=${PLATFORM} ${BASE_IMAGE}

ARG JAVA_VERSION
ARG JAVA_TYPE="jre"
ARG BUILD_TIME
ARG VER

LABEL \
    org.company_name.builder="Maven" \
    org.company_name.compiler="JAVA" \
    org.company_name.java_type=$JAVA_TYPE \
    org.company_name.compiler_version="$JAVA_VERSION" \
    org.opencontainers.image.created=${BUILD_TIME} \
    VERSION=${VER}

ENV JAVA_HOME=/usr/lib/jvm/jre-$JAVA_VERSION-openjdk

ENV PATH=$JAVA_HOME/bin:$PATH

RUN apt-get update && \
    apt-get install -y java-$JAVA_VERSION-openjdk && \
    if [ $JAVA_TYPE == 'jdk' ]; then apt-get install -y java-$JAVA_VERSION-openjdk-devel maven; fi && \
    trust extract --overwrite --format=java-cacerts --filter=ca-anchors --purpose=server-auth $JAVA_HOME/lib/security/cacerts && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
