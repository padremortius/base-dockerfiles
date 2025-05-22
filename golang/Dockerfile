ARG REPO_URL

FROM $REPO_URL/devops-altlinux:p10-1.0.0

ARG GOLANG_VERSION

LABEL \
    org.company_name.compiler="Golang" \
    org.company_name.compiler.version="1.23" \
    org.opencontainers.image.description="Builder image for Company Name's Golang applications"

RUN apt-get update && \
    apt-get install -y golang golang-tools && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
