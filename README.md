# ssup2ket-service-deployment

ssup2ket-service-deployment is the GitOps repository of the ssup2ket services. Because ssup2ket services run on a K8s cluster, it's deployment configuration consists of K8s manifests. The k8s manifest is efficiently configured using [kustomize](https://kustomize.io/). [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) on K8s cluster monitors this repo. When ArgoCD detects changes K8s manifest on this repo, it applies new K8s manifests.

## Install kustomize

* Install kustomize

```
# Ubuntu
$ cd /usr/local/bin
$ curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh" | bash
```

## Deploy manually

* ssup2ket-auth

```
# Dev
$ kustomize build ssup2ket-auth/overlays/dev | kubectl apply -f -

# Prod
$ kustomize build ssup2ket-auth/overlays/prod | kubectl apply -f -
```

## Reference

* Debezium - https://github.com/bykvaadm/debezium-helm-chart
