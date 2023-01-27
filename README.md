
# High-level overview of Containers & Container Orchestration

## Introduction

Containers have become a popular way to package and deploy software, and container orchestration is a method of managing and coordinating containers in a cluster. In this guide, we will provide a high-level overview of containers and container orchestration, and discuss some of the most popular tools and technologies in this space.

### Containers

Containers are a lightweight form of virtualization that allow developers to package an application with all of its dependencies and configurations into a single container. This allows the application to run consistently across different environments.

Containers differ from virtual machines in that they share the host operating system kernel, while virtual machines have their own kernel and emulate hardware. This makes containers more lightweight and efficient than virtual machines.

include:

-   Docker: A platform for developing, shipping, and running applications in containers.
-   lxc: A containerization system that uses Linux kernel features such as namespaces and cgroups to create isolated environments for applications.
-   runc: A command-line tool for creating and managing containers that conform to the Open Container Initiative (OCI) specification.
-   cri-o: A lightweight container runtime for Kubernetes that is designed to be used with the Kubernetes Container Runtime Interface (CRI).
-   containerd: A container runtime that is designed to be used as a daemon to control and manage container lifecycle.
-   podman: A daemonless container engine for developing, managing, and running OCI Containers on your Linux System.

### Container Orchestration

Container orchestration is the process of automating the deployment, scaling, and management of containers. This is necessary to ensure that containers are deployed in a consistent and reliable manner across a cluster of machines.

include:

-   Kubernetes: container orchestration system originally developed by Google.
-   Mesos: cluster manager that can run both containers and non-containerized workloads.
-   Nomad: scheduler that can run both containers and non-containerized workloads.

### Container and Orchestration Tools

|Project|Description|
|-|-|
|Kubernetes| Container orchestration system|
|Apache Mesos|Cluster manager that can run both containers and non-containerized workloads|
|Nomad|Scheduler that can run both containers and non-containerized workloads|
|Docker|Platform for developing, shipping, and running applications in containers|
|lxc|Containerization system that uses Linux kernel features to create isolated environments for applications|
|runc|Command-line tool for creating and managing containers that conform to the Open Container Initiative (OCI) specification|
|cri-o|Lightweight container runtime for Kubernetes|
|containerd|Container runtime that is designed to be used as a daemon to control and manage container lifecycle|
|podman|Daemonless container engine for developing, managing, and running OCI Containers|
|rkt|(deprecated) pod-native container engine for Linux|

### Container Registries

Container images are stored in a container registry. Examples include Docker Hub, Amazon Elastic Container Registry (ECR). It allows teams to store, manage, and distribute container images in a centralized location, making it easier to collaborate and deploy applications.

there are a few key questions to consider when choosing Container Registry, such as whether you need to store additional artifacts beyond container images, if you need extra security features, and whether you prefer an on-prem or hosted solution.

include:

1.  Amazon Elastic Container Registry (ECR) - This registry can be configured to support private and public Docker registries, and comes equipped with features like vulnerability image scanning and immutable image tags.
2.  Azure Container Registry (ACR) - This registry, offered by Microsoft, comes with features like automatic purging of old images, retention policy for untagged manifests, and content trust. It also supports OCI Images, OCI Artifacts, and Helm charts.
3.  Docker Hub Container Registry - This is probably the most popular container registry, and functions as a marketplace for public container images. However, due to some users abusing the auto-build feature to mine cryptocurrencies, there are now limits on Docker’s pull/push image.
4.  GitHub Package Registry - This registry is integrated with GitHub, and allows you to store packages for multiple languages and package managers.
5.  GitLab Container Registry - This registry is integrated with GitLab, and allows for easy storage and management of container images.
6.  Google Artifact Registry (GAR) - This registry is integrated with Google Cloud, and allows you to store and manage container images and other types of artifacts.
7.  Harbor Container Registry - This is an open-source registry that allows for secure storage of container images, and comes with features like role-based access control and image vulnerability scanning.
8.  Red Hat Quay - This registry is offered by Red Hat, and allows for easy storage and management of container images, as well as integration with other Red Hat tools like OpenShift.
9.  Sonatype Nexus Repository OSS - This is an open-source registry that supports multiple package formats, and allows for easy storage and management of container images and other types of artifacts.

In conclusion, there are many options available when it comes to container registries, and the right one for you will depend on your specific needs and preferences. It's important to consider factors such as security, pricing, and additional features when making your decision.

