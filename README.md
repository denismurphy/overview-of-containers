
# High-level overview of Containers & Container Orchestration

## Introduction

Containers have become a popular way to package and deploy software, and container orchestration is a method of managing and coordinating containers in a cluster. In this guide, we will provide a high-level overview of containers and container orchestration, and discuss some of the most popular tools and technologies in this space.

## Containers

Containers are a technology that enables the running of processes in a separated environment alongside other processes on the same computer. This is achieved through the utilization of Linux kernel features, namely "namespaces" and "cgroups".

## Linux Namespaces

Linux namespaces are a feature that creates a virtual machine-like environment, separating the processes. There are several types of Linux namespaces, including:

-   PID namespace, which creates separate processes.
-   Networking namespace, which allows programs to run on any port without conflicting with other processes on the same computer.
-   Mount namespace, which enables the mounting and unmounting of the filesystem without affecting the host filesystem.

Creating a Linux namespace is straightforward, with the use of the unshare package. The command below creates a separate process and assigns the bash shell to it:

`sudo unshare --fork --pid --mount-proc bash` 

## Cgroups

Cgroups is a Linux feature that limits the resources of a process. It determines the limit of CPU and memory that a process can use. To create a cgroup, you need to install cgroup-tools, which can be done with the following commands based on your operating system:

-   Ubuntu and Debian:

`sudo apt-get install cgroup-tools` 

-   CentOS:

`sudo yum install libcgroup` 

Once installed, run the following command to create the cgroup:

`sudo cgcreate -g memory:my-process` 

A folder will be created at the path `/sys/fs/cgroup/memory`, which contains several files that define the limit of the process. The file of interest here is `memory.kmem.limit_in_bytes`, which defines the memory limit of a process in bytes.

For example, to create a process with a memory limit of 50 Mi, run the following command:

`sudo echo 50000000 > /sys/fs/cgroup/memory/my-process/memory.limit_in_bytes` 

To use the cgroup, run the following command:

perl

`sudo cgexec -g memory:my-process <process-name>` 

In summary, containers are a powerful technology that enables the creation of isolated environments for processes, with the ability to limit their resources using cgroups.

examples of popular container tools includes:

-   Docker: A platform for developing, shipping, and running applications in containers.
-   lxc: A containerization system that uses Linux kernel features such as namespaces and cgroups to create isolated environments for applications.
-   runc: A command-line tool for creating and managing containers that conform to the Open Container Initiative (OCI) specification.
-   cri-o: A lightweight container runtime for Kubernetes that is designed to be used with the Kubernetes Container Runtime Interface (CRI).
-   containerd: A container runtime that is designed to be used as a daemon to control and manage container lifecycle.
-   podman: A daemonless container engine for developing, managing, and running OCI Containers on your Linux System.

## Container Registries

Container images are stored in a container registry. Examples include Docker Hub, Amazon Elastic Container Registry (ECR). It allows teams to store, manage, and distribute container images in a centralized location, making it easier to collaborate and deploy applications.

there are a few key questions to consider when choosing Container Registry, such as whether you need to store additional artifacts beyond container images, if you need extra security features, and whether you prefer an on-prem or hosted solution.

examples of container registries popular includes:

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

## Container Orchestration

Container orchestration is the process of automating the deployment, scaling, and management of containers. This is necessary to ensure that containers are deployed in a consistent and reliable manner across a cluster of machines.

examples of popular container orchestration platforms includes:

-   Kubernetes: container orchestration system originally developed by Google.
-   Mesos: cluster manager that can run both containers and non-containerized workloads.
-   Nomad: scheduler that can run both containers and non-containerized workloads.

## Container and Orchestration Tools

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
