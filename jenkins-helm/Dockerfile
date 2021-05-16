FROM ghcr.io/ragin-lundf/k8s-jenkins-docker/k8s-jcasc-jenkins-base:latest

ARG KUBE_VERSION="1.21.0"
ARG HELM_VERSION="3.5.4"
ARG HELMFILE_VERSION="0.139.6"
ARG USER="jenkins"
ARG GROUP="jenkins"
ARG HOMEDIR="/home/${user}/agent"

RUN microdnf update -y && \
    microdnf clean all

RUN wget -q https://storage.googleapis.com/kubernetes-release/release/v${KUBE_VERSION}/bin/linux/amd64/kubectl -O /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    wget -q https://get.helm.sh/helm-v${HELM_VERSION}-linux-amd64.tar.gz -O - | tar -xzO linux-amd64/helm > /usr/local/bin/helm && \
    chmod +x /usr/local/bin/helm && \
    helm repo add "stable" "https://charts.helm.sh/stable" --force-update && \
    wget -q https://github.com/roboll/helmfile/releases/download/v${HELMFILE_VERSION}/helmfile_linux_amd64 && \
    mv helmfile_linux_amd64 /usr/local/bin/helmfile && chmod +x /usr/local/bin/helmfile

