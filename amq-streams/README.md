# AMQ Streams Operator

Installs AMQ Streams operator into all namespaces

:warning: NERVER use the `base` directory directly, since the `channel` and `version` needs to be patch base on the version of Openshift being used or the version of the operator needed.

The current *overlays* available:
* [stable](overlays/stable)

## Usage

There is 3 options to use run this installation:

#### Options 1: Clone the git repo

```
https://github.com/froberge/openshift-catalog.git
```

and then apply the desired overlays from the root directoty

```
oc apply -k amq-streams/overlays/<channel>
```

#### Option 2: Apply directly from GitHub

```
oc apply -k https://github.com/froberge/openshift-catalog/amq-streams/overlays/<channel>
```

#### Option 3: From another overlays in another project

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

bases:
  - github.com/froberge/openshift-catalog/amq-streams/overlays/<channel>?ref=main
```