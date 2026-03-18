# kube-aggregator

* implements 
  * the [Aggregated API Servers](https://github.com/kubernetes/design-proposals-archive/blob/main/api-machinery/aggregated-api-servers.md) design proposal
* provides
  * API /
    * enable
      * registering API servers
  * ALL aggregated APIs' discovery information 
  * HTTP proxying of requests
    * from clients
    * -- to -- specific API backends

## Purpose

* 1 monolithic API server
  * is split into >1 aggregated servers
* ANYONE
  * could write their own aggregated API server / expose their APIs
* cluster admins
  * should be able to expose NEW APIs | runtime

## Compatibility

* HEAD of this repo will match -- HEAD of `k8s.io/apiserver`, `k8s.io/apimachinery`, and `k8s.io/client-go`
