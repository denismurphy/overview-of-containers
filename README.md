# 🐳 Overview of Containers & Orchestration

## 📚 Introduction

Containers have revolutionized software packaging and deployment, while container orchestration manages and coordinates containers in clusters. This guide provides a high-level overview of these technologies and popular tools in the field.

## 📦 Containers

Containers are a technology enabling isolated process execution alongside other processes on the same computer, utilizing Linux kernel features like "namespaces" and "cgroups".

### 🔀 Linux Namespaces

Linux namespaces create virtual machine-like environments, separating processes. Types include:

- 🆔 PID namespace: Creates separate processes
- 🌐 Networking namespace: Allows programs to run on any port without conflicts
- 💾 Mount namespace: Enables filesystem mounting without affecting the host

Example command to create a separate process:
```bash
sudo unshare --fork --pid --mount-proc bash
```

### 🔧 Cgroups

Cgroups limit process resources, determining CPU and memory usage. To create a cgroup:

1. Install cgroup-tools:
   - Ubuntu/Debian: `sudo apt-get install cgroup-tools`
   - CentOS: `sudo yum install libcgroup`

2. Create the cgroup:
   ```bash
   sudo cgcreate -g memory:my-process
   ```

3. Set memory limit (e.g., 50 Mi):
   ```bash
   sudo echo 50000000 > /sys/fs/cgroup/memory/my-process/memory.limit_in_bytes
   ```

4. Use the cgroup:
   ```bash
   sudo cgexec -g memory:my-process <process-name>
   ```

### 🛠️ Popular Container Tools

- 🐋 Docker
- 📦 lxc
- 🏃 runc
- 🚀 cri-o
- 🎛️ containerd
- 🐼 podman

## 🗄️ Container Registries

Container registries store and manage container images. Popular options include:

1. 🌟 Amazon Elastic Container Registry (ECR)
2. 🔵 Azure Container Registry (ACR)
3. 🐳 Docker Hub Container Registry
4. 🐙 GitHub Package Registry
5. 🦊 GitLab Container Registry
6. 🌈 Google Artifact Registry (GAR)
7. ⚓ Harbor Container Registry
8. 🎩 Red Hat Quay
9. 🔷 Sonatype Nexus Repository OSS

## 🎭 Container Orchestration

Container orchestration automates deployment, scaling, and management of containers across machine clusters.

Popular platforms:
- ☸️ Kubernetes
- 🌐 Mesos
- 🚀 Nomad

## 🔧 Container and Orchestration Tools

| Project | Description |
|---------|-------------|
| ☸️ Kubernetes | Container orchestration system |
| 🌐 Apache Mesos | Cluster manager for containers and non-containerized workloads |
| 🚀 Nomad | Scheduler for containers and non-containerized workloads |
| 🐳 Docker | Platform for container development, shipping, and running |
| 📦 lxc | Containerization system using Linux kernel features |
| 🏃 runc | CLI tool for OCI-compliant containers |
| 🚀 cri-o | Lightweight Kubernetes container runtime |
| 🎛️ containerd | Container runtime daemon |
| 🐼 podman | Daemonless container engine |
| 🚀 rkt | (deprecated) Pod-native container engine for Linux |
