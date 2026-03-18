# apiextensions-apiserver

* goal
  * implementation -- for -- `CustomResourceDefinitions`
    * == delegate server | `kube-apiserver`

* implements https://github.com/kubernetes/design-proposals-archive/blob/main/api-machinery/thirdpartyresources.md

* provides
  * API -- for -- registering `CustomResourceDefinitions`

## Compatibility

* this repo's HEAD  == HEAD of "k8s.io/apiserver" & "k8s.io/apimachinery" & "k8s.io/client-go"
