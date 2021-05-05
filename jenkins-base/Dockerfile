ARG UBI_CORE_VERSION=ubi8
ARG UBI_TAG_VERSION=latest

FROM registry.access.redhat.com/${UBI_CORE_VERSION}/ubi-minimal:${UBI_TAG_VERSION}

ARG VERSION=1.0.0
LABEL Description="Jenkins Base Container" Vendor="K8S_MGMT" Version="${VERSION}"

# Jenkins user settings
ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000
ARG AGENT_WORKDIR=/home/${user}/agent

# GLIBC-ENVIRONMENT
ENV GLIBC_LANG=en_US
ENV LANG=${GLIBC_LANG}.UTF-8
ENV LANGUAGE=${GLIBC_LANG}.UTF-8

# install base packages
RUN microdnf update -y && \
    microdnf install -y shadow-utils xz tar zip unzip sudo curl wget bash git procps ca-certificates glibc glibc-langpack-en &&  \
    microdnf clean all

# create jenkins user
RUN groupadd -g ${gid} ${group} && useradd -d /home/${user} -u ${uid} -g ${group} ${user}

# setup jenkins directories and permissions
RUN mkdir /home/${user}/.jenkins && mkdir -p ${AGENT_WORKDIR}

VOLUME /home/${user}/.jenkins
VOLUME ${AGENT_WORKDIR}

WORKDIR /home/${user}

ENTRYPOINT ["tail", "-f", "/dev/null"]
