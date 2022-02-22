## Dev/Test Cluster
1. minikube
2. docker-desktop (windows, macOs)
3. micro-k8s (Ubuntu +)

## Product based on kubernetes
RedHat has built "Open Shift"

Oracle Linux & RHEL Linux
  - Minishift // relatively heavier than minikube

Kubernetes is not built to LAST longer, kubernetes is built to FAIL FAST and RECOVER !

```yaml
nodeSelector:
	kubernetes.io/name: node1
```

## Cattle Vs Pets

Pets   : We make them LIVE longer, Visit vet clinic everytime !
Cattle : Keep the numbers, shorter lifespan. Replace the old ones with new once.


In Kubernetes, Application containers are treated like cattles, individual app-instance / pod is not important, the COUNT of important.

Pod will contain MINIMUM 1 container.


