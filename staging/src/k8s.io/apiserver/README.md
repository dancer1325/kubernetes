# apiserver

* == generic library /
  * allows
    * building a Kubernetes aggregated API server / has
      * delegated authentication & authorization
      * `kubectl` compatible discovery information
      * admission chain
      * versioned types
  * used by
    * `k8s.io/kubernetes`
    * `k8s.io/kube-aggregator`
    * `github.com/kubernetes-incubator/service-catalog`

