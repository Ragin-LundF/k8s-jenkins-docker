FROM ghcr.io/ragin-lundf/k8s-jenkins-docker/k8s-jcasc-jenkins-base:latest

# NODEJS Version (default; will be overwritten by Jenkinsfile)
ARG NODEJS_VERSION=v14.16.1
LABEL Description="Jenkins Worker image for NodeJS" Vendor="K8S_MGMT" Version="${NODEJS_VERSION}"
# NODEJS Version (default; will be overwritten by Jenkinsfile)
ENV NODEJS_HOME /usr/lib/nodejs
ENV PATH ${PATH}:${NODEJS_HOME}/bin

# GET NODEJS/NPM FROM NODEJS.ORG
RUN     wget https://nodejs.org/dist/${NODEJS_VERSION}/SHASUMS256.txt && \
        NODE_NAME=$(awk '/linux-x64.tar.xz/ {print $2}' SHASUMS256.txt)  && \
        NODE_APP=$(echo ${NODE_NAME} | awk -F\.tar '{print $1}') && \
        wget https://nodejs.org/dist/${NODEJS_VERSION}/${NODE_NAME} -P /tmp/ && \
        tar -xJf /tmp/*.tar.xz -C /usr/lib/ && \
        echo "Nodeapp: ${NODE_APP}" && \
        rm /tmp/*.tar.xz && \
        ln -s /usr/lib/${NODE_APP} /usr/lib/nodejs && \
        ln -s /usr/lib/nodejs/bin/node /usr/bin/node

RUN echo "PATH=${PATH}" >> /etc/environment