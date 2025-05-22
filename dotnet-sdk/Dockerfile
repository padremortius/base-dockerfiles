ARG REPO_URL

FROM $REPO_URL/devops-altlinux:p10-1.0.0

ARG DOTNET_CORE_VERSION

LABEL \
    org.company_name.compiler=".Net Core" \
    org.company_name.compiler.version="$DOTNET_CORE_VERSION" \
    org.opencontainers.image.description="Builder image for Company Name's .NET Core applications"

RUN apt-get update && \
    apt-get install -y dotnet-sdk-$DOTNET_CORE_VERSION && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
