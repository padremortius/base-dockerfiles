ARG BASE_IMAGE='devops-altlinux:p10-1.0.0'
ARG PLATFORM="linux/arm64"

FROM --platform=${PLATFORM} ${BASE_IMAGE}

ARG DOTNET_VERSION
ARG DOTNET_TYPE='dotnet-sdk'
ARG BUILD_TIME
ARG VER

LABEL \
    org.company_name.compiler=".Net Core" \
    org.company_name.compiler.version="${DOTNET_VERSION}" \
    org.company_name.dotnet.type="${DOTNET_TYPE}" \
    org.opencontainers.image.created=${BUILD_TIME} \
    VERSION=${VER}

RUN apt-get update && \
    case ${DOTNET_TYPE} in \
    aspnet) apt-get install -y dotnet-aspnetcore-runtime-${DOTNET_VERSION};; \
    dotnet) apt-get install -y dotnet-runtime-${DOTNET_VERSION};; \
    dotnet-sdk) apt-get install -y dotnet-sdk-${DOTNET_VERSION};; \
    *) echo "Wrong dotnet type";; \
    esac && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
