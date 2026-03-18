# Legacy Cluster add-ons

* Cluster add-ons
  * == [Kubernetes API resources](https://kubernetes.io/docs/reference/glossary/?all=true)
    * == SAME -- as -- `Service` & `Deployment` / shipped -- with the -- Kubernetes binaries
  * [MORE](https://kubernetes.io/docs/concepts/cluster-administration/addons/)
  * [classes](addon-manager/README.md)
    - Add-ons / will be reconciled
    - Add-ons / if they do NOT exist -> will be created

## Cooperating Horizontal / Vertical Auto-Scaling with "reconcile class addons"

TODO: 
"Reconcile" class addons will be periodically reconciled to the original state given
by the initial config. In order to make Horizontal / Vertical Auto-scaling functional,
the related fields in config should be left unset. More specifically, leave `replicas`
in `ReplicationController` / `Deployment` / `ReplicaSet` unset for Horizontal Scaling,
leave `resources` for container unset for Vertical Scaling. The periodic reconcile
won't clobbered these fields, hence they could be managed by Horizontal / Vertical
Auto-scaler.

## Add-on naming

The suggested naming for most of the resources is `<basename>` (with no version number).
Though resources like `Pod`, `ReplicationController` and `DaemonSet` are exceptional.
It would be hard to update `Pod` because many fields in `Pod` are immutable. For
`ReplicationController` and `DaemonSet`, in-place update may not trigger the underlying
pods to be re-created. You probably need to change their names during update to trigger
a complete deletion and creation.
