* Introduction
* Cluster component
  1. Master / Manager
  2. Worker nodes

## Worker components
  * kubelet
  * container-runtime
  * kubeproxy

## Master/Manager component (Overview)
  * API Server
  * Scheduler
  * etcd
  * Controller-Manager

## Setting up cluster ( kubernetes playground )

Kubernetes cluster types:
  * ON-premise cluster
  * Dev/Test Cluster (Single node cluster) : ex. Minikube, * * Docker-Desktop K8S
  * Cloud Managed (PaaS) Cluster

### API Object Model

  . kubectl (client CLI)
  . kube-config
  . kubectl commands
  . Kubernetes manifests (YAML)

# Day 2 

  * Pod, ReplicaSet, ConfigMap, Secrets, Deployment
  * rolling-updates, self heal, manual scaling 
  * controller-manager 
  * Services & Service Types
  * Ingress (routing services)
  * Volumes
  * Persistent Volumes
	* PV Claims
  * Volume types

### Extending Kubernetes:
  * Helm CLI (Package manager)
  * Install "metrics server", "dashboard"
  * Horizontal Pod Autoscaler
