# harbor

Instalaremos harbor usando el helm oficial.

> REQUISITOS: Tener keycloak desplegado previamente

``` shell
helm repo add harbor https://helm.goharbor.io
helm repo update
kubectl create namespace harbor
## helm show values harbor/harbor --version 1.14.0 > values.default.yaml
kubectl apply -f manifests
helm upgrade --install -f values.yaml harbor harbor/harbor --version 1.14.0 -n harbor --create-namespace
```
