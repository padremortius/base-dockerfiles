ARG REPO_URL

FROM $REPO_URL/devops-altlinux:p10-1.0.0

ARG DOTNET_VERSION

LABEL \
    org.company_name.compiler=".Net Runtime" \
    org.company_name.compiler.version="$DOTNET_VERSION" \
    org.opencontainers.image.description="Image for run Company Name's .NET applications"

RUN apt-get update && \
    apt-get install -y dotnet-runtime-$DOTNET_VERSION && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
