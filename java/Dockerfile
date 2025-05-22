ARG REPO_URL

FROM $REPO_URL/devops-altlinux:p10-1.0.0

ARG JAVA_VERSION
ARG JAVA_TYPE="jre"

LABEL \
    org.company_name.builder="Maven" \
    org.company_name.compiler="JAVA" \
    org.company_name.java_type=$JAVA_TYPE \
    org.company_name.compiler_version="$JAVA_VERSION" \
    org.opencontainers.image.description="Builder image for Company Name's Java application"

ENV JAVA_HOME /usr/lib/jvm/jre-$JAVA_VERSION-openjdk

ENV PATH $JAVA_HOME/bin:$PATH

RUN apt-get update --enable-upgrade && \
    apt-get install -y java-$JAVA_VERSION-openjdk && \
    if [ $JAVA_TYPE == 'jdk' ]; then apt-get install -y java-$JAVA_VERSION-openjdk-devel maven; fi && \
    trust extract --overwrite --format=java-cacerts --filter=ca-anchors --purpose=server-auth $JAVA_HOME/lib/security/cacerts && \
    rm -f /var/cache/apt/archives/*.rpm /var/cache/apt/*.bin /var/lib/apt/lists/*.*
