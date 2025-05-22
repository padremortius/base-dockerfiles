ARG REPO_URL

FROM $REPO_URL/devops-altlinux:p10-1.0.0

ARG DOTNET_VERSION

LABEL \
    org.company_name.compiler="ASP.Net Runtime" \
    org.company_name.compiler.version="$DOTNET_VERSION" \
    org.opencontainers.image.description="Image for run Company Name's ASP.NET applications"

RUN apt-get update && \
    apt-get install -y dotnet-aspnetcore-runtime-$DOTNET_VERSION && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
