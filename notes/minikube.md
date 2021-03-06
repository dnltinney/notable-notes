---
tags: [brew, container, container/k8s]
title: minikube
created: '2019-07-30T06:19:49.146Z'
modified: '2020-11-04T10:51:18.931Z'
---

# minikube

> `minikube` uses `libmachine` see also `docker machine`

## installation
`brew install minikube`

## usage
```sh
minikube completion bash > $(brew --prefix)/etc/bash_completion.d/minikube


MINIKUBE_HOME                         # (string) path for the .minikube dir used for state/configuration
MINIKUBE_IN_STYLE                     # (bool)   whether or not emoji and colors should appear in minikube
MINIKUBE_WANTUPDATENOTIFICATION       # (bool)   sets whether the user wants an update notification for new minikube versions
MINIKUBE_REMINDERWAITPERIODINHOURS    # (int)    sets the number of hours to check for an update notification
MINIKUBE_ENABLE_PROFILING             # (int, 1 enables it) enables trace profiling to be generated for minikube

# ~/.minikube/config/config.json
minikube config set cpus 2
minikube config set memory 4096
minikube config set kubernetes-version latest
minikube config view

export MINIKUBE_IN_STYLE=false      # disable emojis
minikube start \
  --driver=virtualbox --cpus=4 --memory='4096' \
  --kubernetes-version=latest --nodes=1 \
  --addons=metrics-server
#  --container-runtime=cri-o
#  --cache-images


minikube start --nodes 2 -p multinode-demo      # start multpile nodes
minikube stop
minikube delete                                 # clear local state

minikube status

minikube dashboard
kubectl config view --namespace kubernetes-dashboard

minikube ssh

minikube ip

minikube service list
minikube service SERVICE_NAME                   # open exposed endpoint in browser
minikube service SERVICE_NAME --url --namespace=NAMESPACE

# addons
minikube addons list
minikube addons enable metrics-server     # needed for `kubectl top node`
minikube addons enable ingress            # provisions: configMap, ingress-controller and service (exposes default nginx-pod; handles unmapped requests)
```

## see also
- [minikube.sigs.k8s.io/docs/](https://minikube.sigs.k8s.io/docs/)
- [[kubectl]]
- [[kubernetes]]
- [[argocd]]
