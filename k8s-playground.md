# Kubernetes Playground : walkthrough

1. Visit https://labs.play-with-k8s.com/ and login with docker-id
2. Use "Add New Instance" button TWO times
3. Select "node1" from left side panel, run following command (Paste => Shift+INSERT)
	
	```
	kubeadm init --apiserver-advertise-address $(hostname -i) --pod-network-cidr 10.2.0.0/16
	```
4. Wait for command execution to COMPLETE, once it completes, it MUST print "command to be run" on worker node
5. Copy the command from output (Two lines and it begins with kubeadmin join)
6. From left-side menu click on "node2" and paste command (Shift+INSERT) and press ENTER
7. Go back to node1 and run next command to install kube-network.

	```bash
	kubectl apply -f https://raw.githubusercontent.com/cloudnativfelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml
	```
8.  Just wait for 2 minutes and then try following command to check if both node1 and node2 are Ready

	```
	kubectl get nodes
	```

9.	Clone kubernetes-demos github repository
	
	cd ~
	git clone https://github.com/mahendra-shinde/kubernetes-demos
	cd kubernetes-demos

