
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
