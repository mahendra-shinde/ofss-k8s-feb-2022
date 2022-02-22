# Kube Config

1. KubeConfig is `credentials` file, provides information & secrets (keys) to access remote kubernetes cluster.
2. Standard location for kubecofig file:
	
	Windows : C:\Users\mahendra\.kube\config	
	MacOS   : /Users/mahendra/.kube/config
	Linux   : /home/mahendra/.kube/config

	> Note: Kindly replace "mahendra" with your login-name.

3. Only `Kubernetes Administrator` is suppose to create/edit this file.
4. Kube Config will then be used by CLI Client tools
	kubectl

## KubeCTL

Kubernetes Client CLI 

Command Syntax:

$ kubectl [verb] [options]

Sr.No|Example  | Description
--|------|---------------
1. | $ kubectl cluster-info | Shows cluster information, usually for TESTING connectivity with cluster.
2. | $ kubectl get nodes | List all nodes (includes master and worker)
3. | $ kubectl describe node node1 | Get details of node 'node1'
4. | $ kubectl config get-contexts | List all cluster-contexts
5. | $ kubectl config get-clusters | List all clusters

Kubernetes Object Types and their abbreviations 

Full Name | Short form | Plural form
----------|------------|--------------
node | no | nodes
pod	 | po | pods
replicaset | rs | replicasets
service | svc  | services
Deployment | deploy | deployments
statefulset | sts | statefulsets
persistentvolume | pv | persistentvolumes
storageclass | sc | storageclasses
configmap | cm | configmaps
secret | secret | secrets
namespace | ns | namespaces
ingress | ing | ingresses





