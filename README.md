# OpenShift Catalog

This OpenShift Catalog uses [Kustomize](https://kustomize.io/) to deploy a number of Operators or applications that could be needed when deploying an OpenShift cluster.

:warning: **This catalog is my own work and is not supported by Red Hat** and I strongly discouraged you from referencing this repo directly as a remote Kustomize repo. It also rely on the a [GitOps Catalog](https://github.com/redhat-cop/gitops-catalog) that is not supported by Red Hat. Instead we engouraged you to take indidual items of interest and curated in your own catalog and maintain it as your own.

The purpuse of this catalog is for experimentation and facilitate cluster preparation for demo.

## Usage

Each application or operators while be define in it own directory. You can usually just apply to required Kustomize using the `-k` flag directly in your `oc` CLI or `kubectl` CLI. If more specification is needed on a catalog component a README file will be provided. Here how to use a compoents:

1. By cloning the the catalog locally and applying the desired kustomize like so:
    ```
    git clone https://github.com/froberge/openshift-catalog
    oc apply -k openshift-catalog/nexus/base
    ```

2. Referencing directly the repository in you `CLI` apply commmand like so:
    ```
    oc apply -k https://github.com/froberge/openshift-catalog/nexus/base
    ```

## Kustomize

Various tools here can be reference in your own Kustomize scripts without you explicitly cloning the catalog repo, for example:

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

namespace: [DEFINE YOUR NAMESPACE]

resources:
- github.com/froberge/openshift-catalog/nexus/base/?ref=main
```

**Note** none of the catalog component specify a namespace, in your kustomization overlay you can include the specific namespace you want to install the tool into.