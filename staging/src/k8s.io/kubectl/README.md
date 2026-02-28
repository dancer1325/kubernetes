# Kubectl

* 's packages
  * uses
    * by client programs
      * _Examples:_ these packages are vendored into `k8s.io/kubernetes` for use in
        the [kubectl](https://github.com/kubernetes/kubernetes/tree/master/cmd/kubectl)
        cli client
  * design:
    * interfaces
      * sensible
      * small
    * import a limited set of dependencies
