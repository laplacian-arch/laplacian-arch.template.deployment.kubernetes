# laplacian-arch:template:deployment.kubernetes

A laplacian template module providing a set of scripts which deploy the entire application to a kubernetes
cluster as a helm-package.
Currently, deploying to k8s clusters on Google Kubernetes Engine (GKE)
and local clusters on Docker for Desktop are supported.
SSL with automated certification by Let's encrypt is enabled by default when deploying on GKE.



## Getting started

Firstly, you need to add the following entry to your `laplacian-module.yml` :

```yaml
project:
  group: ${your.project.group}
  name: ${your.project.name}
  type: project
  version: "1.0.0"
  templates:
  ## ↓↓ ADD ↓↓ ##
  - group: laplacian-arch
    name: deployment
    subname: kubernetes
    version: "1.0.0"
  ## ↑↑ ADD ↑↑ ##
```

To reflect the change, you need to type the following command in your console :
```bash
./gradlew lM
```

Then put some model files under the *./model* directory and type the following command to generate files:
```bash
./gradlew lG
```