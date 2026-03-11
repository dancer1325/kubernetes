# Kubernetes hack GuideLines

* goal
  * scripts / 
    * ensure continuous development of kubernetes
    * enhance the robustness of the code
    * improve development efficiency
    * etc.

## Key scripts

* [`verify-all.sh`](verify-all.sh)
  * vestigial redirection
  * ❌NOT add "real" logic❌
  * == `make verify`
  * uses
    * BEFORE submitting a PR
* [`update-all.sh`](update-all.sh)
  * vestigial redirection
  * ❌NOT add "real" logic❌
  * == `make update`
  * uses
    * if ANYTHING fails

## how to run?
* | [root directory](../) 
