# code-generator

* Golang code-generators /
  * uses
    * 👀implement [Kubernetes-style API types](https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md)👀
    * | 
      * [CustomResourceDefinition](https://kubernetes.io/docs/tasks/access-kubernetes-api/extend-api-custom-resource-definitions/), to build native & versioned
        * clients
        * informers
        * helpers
      * [User-provider API Servers](../apiserver), to build conversions BETWEEN 
        * internal -- & -- versioned types, defaulters, protobuf codecs,
        * internal -- & -- versioned clients & informers

## how to use?

* [kube_codegen.sh](kube_codegen.sh)
  * recommended script -- to -- use 
* [| CustomResources](https://cloud.redhat.com/blog/kubernetes-deep-dive-code-generation-customresources/)
* _Example:_ [sample controller](../sample-controller)

## Compatibility

* this repo's HEAD == HEAD of 
  * "k8s.io/apiserver"'s HEAD
  * "k8s.io/apimachinery"'s HEAD
  * "k8s.io/client-go"'s HEAD
