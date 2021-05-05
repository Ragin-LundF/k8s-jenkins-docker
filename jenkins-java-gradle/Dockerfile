FROM ghcr.io/ragin-lundf/k8s-jenkins-docker/k8s-jcasc-jenkins-base-java:latest

# Gradle Version (default; will be overwritten by Jenkinsfile)
ARG GRADLE_VERSION=7.0
LABEL Description="Jenkins Worker image for Gradle" Vendor="K8S_MGMT" Version="${GRADLE_VERSION}"
# Gradle version
ENV GRADLE_HOME=/opt/gradle-${GRADLE_VERSION}
ENV PATH ${PATH}:${GRADLE_HOME}/bin

# Get Gradle from services.gradle.org
RUN wget https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip && \
    unzip -d /opt gradle-${GRADLE_VERSION}-bin.zip && \
    rm *.zip
