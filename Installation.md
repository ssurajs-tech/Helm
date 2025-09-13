
# Helm Commands Installation Guide

This guide provides step-by-step instructions to install and set up **Docker**, **kubectl**, **Minikube**, and **Helm**, along with creating your first Helm chart for Kubernetes.  

## Table of Contents
- [Install Docker](#install-docker)  
- [Install kubectl](#install-kubectl)  
- [Install Minikube](#install-minikube)  
- [Start Minikube](#start-minikube)  
- [Download Helm](#download-helm)  
- [Verify the installation](#verify-the-installation)  
- [Create Your First Helm Chart](#create-your-first-helm-chart)  
- [Check version of the helm](#check-version-of-the-helm)  

***

## Install Docker
```bash
sudo apt update && apt -y install docker.io
```

***

## Install kubectl
```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl \
  && chmod +x ./kubectl \
  && sudo mv ./kubectl /usr/local/bin/kubectl
```

***

## Install Minikube
```bash
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
  && chmod +x minikube \
  && sudo mv minikube /usr/local/bin/
```

***

## Start Minikube
```bash
apt install conntrack
minikube start --vm-driver=none --force
```

If the above command does not work, use:
```bash
minikube start --force
```

Check Minikube status:
```bash
minikube status
```

***

## Download Helm
```bash
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

***

## Verify the installation
```bash
which helm
```

***

## Create Your First Helm Chart
```bash
helm repo add stable https://charts.helm.sh/stable
helm install testchart2 stable/tomcat --set service.type=NodePort
```

***

## Check version of the helm
```bash
helm version
```

