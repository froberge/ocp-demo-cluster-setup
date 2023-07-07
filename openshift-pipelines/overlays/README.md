Installs the `stable channel` of the OpenShift Pipelines Operator.

:warning: NERVER use the `base` directory directly, since the `channel` and `version` needs to be patch base on the version of Openshift being used or the version of the operator needed.

The current *overlays* available:
* [stable](overlays/stable) -> The latest stable version
* [latest](overlays/latest) `shouldn't be use in a production environment`
* [version](overlays/version) -> Use this to specify a particular version.

