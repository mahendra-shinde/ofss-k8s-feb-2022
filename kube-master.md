# Kubernetes Master Node components

## Common Component

Component Name | Description
---------------|------------
Container Runtime | Kubernetes can use ANY OCI-Compliant Runtime, example : docker, libcontainer, cri-o
Kubelet | A Linux Daemon or Windows service. Communicates (gossip) with API-Server. API Server will declare a "node not-available" or "Not ready" if it does not receive any communication from kubelet.
Kube-proxy | Networking proxy, allows "external users/clients" to communicate with workload / application deployed in cluster.


## Control-Plane components

Component Name | Description
---------------|------------------
Scheduler   | Takes "decision" for creating / deleting pod (containers). Also decides "where" to deploy certain pod.Actual creation/deletion of containers is "DONE" by "kubelet".
ETCD | NoSQL Database, stores all cluster information.
API-Server | REST Api accessible to "Developers" and "Administrator". Kubelet always communicates with API-Server !
Controller-Manager | Collection of several controllers. Each controller managed single object type, eg. replicaset-controller, service-controller, deployment-controller. 

## Example Scenario

> A "Developer" want to deploy THREE copies (pods) of application to kubernetes cluster

```bash
$ kubectl apply -f myapp.yaml
```

## Communication flow
1. KUBECTL uploads "myapp.yaml" to API-Server
2. API Server will then "STORE" the contents iniside etcd data-store
3. Choose "COntroller" from "Controller-manager" based on "Kind" attribute of "YAML" file.
4. Deployment-Controller will then "request" scheduler to create the required number of pods
5. Scheduler will just identify, where new pods should be deployed (which nodes)
6. Scheduler will send ORDER to kubelet (Via API-SERVER) to create pod (containers)
7. Kubelet will ORDER container runtime to create container, and then INFORM API-Server whether containers are created successfuly!