# api

* external API types' schema / served -- by the -- Kubernetes API server
  * == Kubernetes API definition
  * how to use?
    * dependency of client-go
  * published separately
    * Reason: 🧠if you use `k8s.io/client-go` + `k8s.io/apimachinery` + `k8s.io/apiserver` + ... avoid diamond dependency 🧠

## recommendations

* use the go types | this repo
* TODO: you may serialize them -- directly to -- JSON

If you want to store or interact with proto-formatted Kubernetes API objects, we
recommend using the "official" serialization stack in `k8s.io/apimachinery`.
Directly serializing these types to proto will not result in data that matches
the wire format or is compatible with other kubernetes ecosystem tools
* Reason: 🧠[wire format includes a magic prefix + envelope proto](https://kubernetes.io/docs/reference/using-api/api-concepts/#protobuf-encoding)🧠


For the same reason, we do not recommend embedding these proto objects within
your own proto definitions
* It is better to store Kubernetes objects as byte
arrays, in the wire format, which is self-describing
* This permits you to use
either JSON or binary (proto) wire formats without code changes
* It will be
difficult for you to operate on both Custom Resources and built-in types
otherwise.
