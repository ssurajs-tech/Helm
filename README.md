# Helm

# Overview

Helm is a package manager for Kubernetes that simplifies the deployment, management, and scaling of applications using Helm charts. This README provides an overview of Helm, its components, architecture, and why it is widely used in Kubernetes environments.

---

## Table of Contents
- [Introduction](#introduction)
- [Why use Helm](#why-use-helm)
- [Keywords/Components in Helm](#keywordscomponents-in-helm)
  - [Charts](#charts)
  - [Release](#release)
  - [Repository](#repository)
- [Helm Architecture](#helm-architecture)
- [Helpful Helm Commands](#helpful-helm-commands)
- [Additional Notes](#additional-notes)

---

## Introduction
- Introduced first time in 2015.
- Helm helps you to manage Kubernetes applications with Helm charts, which let you define, install, and upgrade even the most complex Kubernetes applications.
- Helm is equivalent to yum and apt.
- Helm is now part of the official Kubernetes project and is part of CNCF as well.
- The main building block of Helm is based on deployments using Helm charts.
- These charts describe a configurable set of dynamically generated Kubernetes resources.
- The charts can be stored locally or fetched from remote chart repositories.

---

## Why use Helm
- Writing and maintaining Kubernetes manifest files for all the required Kubernetes objects can 
  be a time-consuming and tedious task. For the simplest of deployments, you would need at least 
  three YAML manifest files with duplicate and hardcoded values.
- Helm simplifies this process by creating a single package that can be deployed to your cluster. Helm 3 was released in November 2019.
- It automatically maintains a database of all versions of your releases, so whenever something 
  goes wrong during deployment, you can roll back to the previous state with a single command.

---

## Keywords/Components in Helm

### Charts
Helm charts are simply Kubernetes manifests combined into a single package that can be deployed to your Kubernetes cluster.  
A chart is a Helm package that contains all the necessary resource definitions to run an application, tool, or service inside a Kubernetes cluster.  
Think of it as the Kubernetes equivalent of a Homebrew formula, apt, yum, or rpm file.

### Release
A release is an instance of a chart running in a Kubernetes cluster.  
One chart can often be installed many times into the same cluster.  
Each time it is installed, a new release is created.  

Consider a MySQL chart: if you install that chart twice, each installation will have its own release with its own release name.

### Repository
A repository is a location where packaged charts can be stored and shared.

---

## Helm Architecture
1. Helm is a single-service architecture or one executable architecture responsible for implementing Helm charts.
2. There is neither a client-server split nor is the core processing logic distributed among components.
3. Implementation of Helm 3 is a single command line client with no in-cluster server or controller.
4. This tool exposes command line operations and unilaterally handles the package management process.

---

## Helpful Helm Commands

Below are some common Helm commands you can use in your Kubernetes environment:



---

## Additional Notes
- Helm is often described as the "Package Manager for Kubernetes."
- Helm 3 consolidated its architecture into a **single CLI tool**, removing the need for server-side components (`Tiller` was part of Helm 2 but is removed in Helm 3).
- Helm provides the foundations for GitOps-style workflows, enabling CI/CD pipelines to automate deployments.

---


