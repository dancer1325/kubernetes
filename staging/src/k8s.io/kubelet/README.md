# kubelet

* provides
  * `ComponentConfig` API types
    * external
    * versioned
    * allows
      * configuring the kubelet
    * uses
      * by third-party tool, writing Kubernetes `ComponentConfig` objects

## Notes
* implement [KEP 14 - Moving ComponentConfig API types to staging repos](https://git.k8s.io/enhancements/keps/sig-cluster-lifecycle/wgs/115-componentconfig/README.md#kubelet-changes)

## Compatibility

* this repo's HEAD == 
  * k8s.io/apiserver's HEAD
  * k8s.io/apimachinery's HEAD
  * k8s.io/client-go's HEAD
