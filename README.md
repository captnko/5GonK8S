# 5GonK8S
Emulation of 5G images on a Kubernetes cluster deployed locally as k3s nodes using k3d project

## Introduction

The aim of this project is to emulate a full 5G environment in order to provide a useful testbed for different scenarios and evaluations. The following steps show how to start by a single laptop and become able to run a full testbed on a locally deployed Kubernetes cluster.

The following solutions and projects used have been selected as best fitted for the work. 

## 0. Ubuntu installation and configuration

For present work the OS used has been Ubuntu 18.04 LTS https://releases.ubuntu.com/18.04/

This answer seems exaustive for: "How to install Ubuntu 18.04 LTS alongside Windows 10?"
--> https://askubuntu.com/questions/1031993/how-to-install-ubuntu-18-04-alongside-windows-10

## 1. Kubernetes local cluster

Once Ubuntu has been installed correctly it is necessary to install Docker and deploy Kubernetes local cluster.

### Docker installation

Install Docker https://www.docker.com/

### k3s/k3d

Use k3d to deploy a Kubernetes cluster with Docker containers as Kubernetes cluster nodes without Flannel networking. https://k3d.io/

### kubectl installation

Install kubectl to administrate better the cluster: https://v1-18.docs.kubernetes.io/docs/tasks/tools/install-kubectl/

### Calico networking

Then configure Calico netowrking as described on official website: https://www.projectcalico.org/

## 2. 5G emulation

The images used as base for the Docker container images are: https://github.com/LABORA-INF-UFG/NetSoft2020-Tutorial4

They have been modified and re-uploaded to Docker Hub, then used for the Kubernetes manifests to deploy 4G components.

Use manifests with "kubectl apply -f <<name_of_manifest.yaml>>" to deploy 5G components.

## 3. Testing

### ping

Ping from UE through tunnel interface to internet.

## References

LABORA projects and k3d have been great tools used to deploy this environment.



