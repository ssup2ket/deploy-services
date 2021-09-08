# ssup2ket Deploy

## Install kustomize

* Install kustomize

```
# Ubuntu
$ cd /usr/local/bin
$ curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
```

## Deploy

* ssup2ket-auth

```
# Dev
$ kustomize build ssup2ket-auth/overlays/dev | kubectl apply -f -

# Prod
$ kustomize build ssup2ket-auth/overlays/prod | kubectl apply -f -
```

