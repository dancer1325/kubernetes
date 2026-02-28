* `kubectl rollout`
  * allows
    * managing the rollout of >=1 resources
      * ALLOWED |
        * deployments
        * daemonsets
        * statefulsets
  * `kubectl rollout undo someValidRolloutResource/nameOfResource`
    * rollback -- to the -- previous deployment
  * `kubectl rollout status someValidRolloutResource/nameOfResource`
    * check the rollout status of "someValidRolloutResource/nameOfResource"
  * `kubectl rollout restart someValidRolloutResource/nameOfResource`
    * restart "someValidRolloutResource/nameOfResource"
  * `kubectl rollout restart someValidRolloutResource/nameOfResource`
    * restart deployments
