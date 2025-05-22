ARG REPO_URL

FROM $REPO_URL/devops-altlinux:p10-1.0.0

LABEL \
    org.company_name.builder="Pip" \
    org.company_name.compiler="Python" \
    org.opencontainers.image.description="Image for build and run Company Name's python applications"

RUN apt-get update && \
    apt-get install -y python3-module-pip && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
