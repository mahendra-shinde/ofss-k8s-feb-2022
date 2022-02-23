# Using private registry for images

1. Create "docker-registry" secret that contains your register server url, username & password
	 $LOGINSERVER="acr098.azurecr.io"
	 $USERNAME="acr098"
	 $PASSWORD="aGo+5s2JsdkfXOmrx4xmtSLKnYQrfnsR"
	$ kubectl create secret docker-registry reg1 --docker-server=$LOGINSERVER --docker-username=$USERNAME --docker-password=$PASSWORD

2. Create a Pod with Private Image.

	kubectl apply -f test-app.yml
	kubectl get po app10
	kubectl describe po app10