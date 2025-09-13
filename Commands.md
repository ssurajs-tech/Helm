
***
# Helm Commands Guide

This file contains a list of common **Helm commands** used for managing Helm charts and releases. Each section details relevant commands grouped by their functionality.  

---

## Table of Contents
- [Repository Management](#repository-management)
- [Searching Charts](#searching-charts)
- [Showing Chart Information](#showing-chart-information)
- [Installing Charts](#installing-charts)
- [Creating Charts](#creating-charts)
- [Getting Release Information](#getting-release-information)
- [Listing Releases](#listing-releases)
- [Viewing Release Status](#viewing-release-status)
- [Viewing Release History](#viewing-release-history)
- [Deleting Releases](#deleting-releases)
- [Upgrading Releases](#upgrading-releases)
- [Rolling Back Releases](#rolling-back-releases)
- [Pulling Charts](#pulling-charts)

---

## Repository Management
Manage Helm chart repositories.

# List all Helm chart repositories
```
helm repo list
```

# Add a new Helm chart repository
```
helm repo add stable https://charts.helm.sh/stable
```

# Remove a Helm chart repository
```
helm repo remove stablehel
```

---

## Searching Charts
Search for Helm charts inside repositories.

```
helm search repo jenkins
helm search repo tomcat
helm search repo apache
```

---

## Showing Chart Information
Show detailed information about a Helm chart.

```
helm show repo stable/tomcat 
helm show chart stable/tomcat
helm show all stable/tomcat 
```

---

## Installing Charts
Install applications from Helm charts with advanced configuration options.

# Install a chart with a wait and timeout
```
helm install mychart stable/charts --wait --timeout 10S
```
# Install Jenkins chart
```
helm install testjenkins stable/jenkins 
```
# Dry-run installation of Tomcat chart
```
helm install --dry-run testchart stable/tomcat 
```
# Install Tomcat chart with wait and timeout
```
helm install --wait --timeout 20s testtomcat stable/tomcat
```

## There are two ways to pass configuration data during install:


# Install a chart with a specific service type
```
helm install mychart stable/mychart --set service.type=NodePort
```
# Install a Tomcat server chart with a specific service type
```
helm install tomcatserver stable/tomcat --set master.service=NodePort
```
# Install a chart from a local package
```
helm install mychart tomcat-0.4.3.tgz
```
# Install a chart from a URL
```
helm install mychart <URL>
```

## Additional commands:

```
helm install testtomcat stable/tomcat
kubectl get all
helm install testchart stable/tomcat --version 0.4.0
helm list
```

---

## Creating Charts
Create new Helm charts.

```
helm create mychart 
helm create hello-world 
```

---

## Getting Release Information
Retrieve information about existing releases.

```
helm get mychart 
```

---

## Listing Releases
List all Helm releases in your cluster.

```
helm list
```

---

## Viewing Release Status
Display the status of a Helm release.

# Display status of a specific release
```
helm status <release-name>
```
# Example: status of "mychart" release
```
helm status mychart
helm status mysql 
```

---

## Viewing Release History
Show the history of a Helm release.

```
helm history mysql01 /bitnami/mysql 
```

---

## Deleting Releases
Delete a Helm release.

```
helm delete testjenkins 
helm delete testtomcat 
```

---

## Upgrading Releases
Upgrade an existing Helm release.

```
helm install mysql01 bitnami/mysql
helm list
helm upgrade mysql01 bitnami/mysql
```
---

## Rolling Back Releases
Roll back a Helm release to a previous version.

```
helm list
helm history mysql01
helm rollback mysql01
helm history mysql01
helm delete mysql01
helm list 
```

---

## Pulling Charts
Download Helm charts from repositories.

```
helm pull stable/tomcat
ls
helm pull bitnami/mysql --untar
ls
tree mysql/
```

---

## Notes
- Helm simplifies Kubernetes deployments by packaging multiple Kubernetes manifests into a single chart.
- The commands listed here cover common day-to-day operations used in managing Helm charts and releases.
- These should be executed against a Kubernetes cluster with Helm installed and configured.



