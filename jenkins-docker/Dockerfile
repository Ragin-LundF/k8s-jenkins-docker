FROM ghcr.io/ragin-lundf/k8s-jenkins-docker/k8s-jcasc-jenkins-base:latest

RUN microdnf update -y && \
    microdnf install -y yum yum-utils &&  \
    microdnf clean all && \
    yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo && \
    yum-config-manager --add-repo http://mirror.centos.org/centos/8/AppStream/x86_64/os/ && \
    yum update && yum makecache && \
    yum install -y --nogpgcheck docker-ce docker-ce-cli containerd.io && \
    yum clean packages
