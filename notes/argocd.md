---
title: argocd
created: '2020-10-26T12:29:59.372Z'
modified: '2020-10-27T10:15:54.748Z'
---

# argocd

> declarative, gitops continuous delivery tool for k8s

## usage
```sh
argocd login HOST

argocd app create guestbook \
  --repo https://github.com/argoproj/argocd-example-apps.git \
  --path guestbook \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default
```

## see also
- [[kubectl]]
- [[minikube]]
