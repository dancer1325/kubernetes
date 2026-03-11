# Kubernetes's OpenAPI Specification

* Kubernetes API [OpenAPI specification](https://github.com/OAI/OpenAPI-Specification)
  * ⚠️generated ⚠️-- through -- running [`update-openapi-spec.sh`](../../hack/update-openapi-spec.sh)
    * == documentation
    * != use -- as -- specification to generate
      * Reason:🧠Kubernetes API is generated -- from -- source code 🧠

## how is it generated

## Vendor Extensions

* allows
  * extend OpenAPI
    * ⚠️IMPORTANT the Kubernetes version | extensions are added⚠️

### `x-kubernetes-group-version-kind`

Operations and Definitions may have `x-kubernetes-group-version-kind` if they
are associated with a [kubernetes resource](https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources).


For example:

``` json
"paths": {
    ...
    "/api/v1/namespaces/{namespace}/pods/{name}": {
        ...
        "get": {
        ...
            "x-kubernetes-group-version-kind": {
            "group": "",
            "version": "v1",
            "kind": "Pod"
            }
        }
    }
}
```

### `x-kubernetes-action`

Operations and Definitions may have `x-kubernetes-action` if they
are associated with a [kubernetes resource](https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources).
Action can be one of `get`, `list`, `put`, `patch`, `post`, `delete`, `deletecollection`, `watch`, `watchlist`, `proxy`, or `connect`.


For example:

``` json
"paths": {
    ...
    "/api/v1/namespaces/{namespace}/pods/{name}": {
        ...
        "get": {
        ...
            "x-kubernetes-action": "list"
        }
    }
}
```

### `x-kubernetes-list-map-keys`

Operations and Definitions may have `x-kubernetes-list-maps-keys` if they
are associated with a [kubernetes resource](https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources). `x-kubernetes-list-type` = `map` specifies field names inside each list element to serve as unique keys for the list-as-map.

**For example:**

```json
{
  "type": "object",
  "properties": {
    "servers": {
      "type": "array",
      "x-kubernetes-list-type": "map",
      "x-kubernetes-list-map-keys": ["name"],
      "items": {
        "type": "object",
        "properties": {
          "name": { "type": "string" },
          "address": { "type": "string" }
        },
        "required": ["name"]
      }
    }
  }
}
```

### `x-kubernetes-patch-strategy` and `x-kubernetes-patch-merge-key`

* ALLOWED | some definitions
* [MORE](https://git.k8s.io/community/contributors/devel/sig-api-machinery/strategic-merge-patch.md)
