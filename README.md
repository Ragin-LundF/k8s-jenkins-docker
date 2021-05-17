# Repository for Jenkins Docker images

This repository contains the required Docker containers for the example described below in the medium article about Kubernetes and Jenkins JCasC deployments.

More information:
- Medium Article [Kubernetes and CI/CD — How to integrate in your development process](https://ragin.medium.com/kubernetes-and-ci-cd-how-to-integrate-in-your-development-process-9b483b194975)
- Github [k8s-JCasC-Mgmt tool](https://github.com/Ragin-LundF/k8s-jcasc-management-go)
- Github [k8s-JCasC-Mgmt example project](https://github.com/Ragin-LundF/k8s-jcasc-mgmt-example)
- Github [k8s-JCasC-app-example](https://github.com/Ragin-LundF/k8s-jcasc-app-example)
- Github [k8s-JCasC docker containers](https://github.com/Ragin-LundF/k8s-jenkins-docker)
- Github [k8s-JCasC helm charts example](https://github.com/Ragin-LundF/k8s-jcasc-app-helm-charts)
- Github [k8s-JCasC helmfile deployment example](https://github.com/Ragin-LundF/k8s-jcasc-deploy-helmfile-example)


# jenkins-base
Jenkins Base image for non-Java build tools.

# jenkins-docker
Jenkins build image with installed Docker

# jenkins-helm
Jenkins depoy image with helm, helmfile and kubectl

# jenkins-java
Jenkins Base image for Java build tools.

# jenkins-java-gradle
Jenkins build image with installed Gradle

# jenkins-node
Jenkins build image with installed NodeJS
