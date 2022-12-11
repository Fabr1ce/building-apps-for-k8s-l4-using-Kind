# building-apps-for-k8s-l4

This repository is used to build a k8's cluster locally for testing using _kind_. The assumption here is that docker and kind are aleady installed locally, if not use the following links to install docker (https://docs.docker.com/engine/install/) and kind (https://kubernetes.io/docs/tasks/tools/).

1 - First _kind_ is used to spin up a k8's cluster, _minikube_ or _docker desktop_ can also be used here:

	kind create cluster
  
The created cluster is verified using the following cmds:
	
	kind get clusters 

which return the name of the cluster (kind)

	kubectl get cluster-info 

returns the k8's master and kubeDNS info
  
	kubectl config get-contexts 

returns inactive and active contexts (kind-kind)
  
	kubectl get nodes 

returns the kube-control-plane
  
	kubectl get all -A 
    
returns all the nodes spun up by _kind_ to launch the k8's cluster

2 - Second, k8's is used with the yaml file to launch a pod:
    
	kubectl apply -f pod.yaml 
		
which returns the name of the pod created
    
	kubectl get pods 
			
which lists the new pod and its status

3 - Clean up:

Delete pods
   
	 kubectl get pods

then   
	 
	 kubeclt delete pod building-apps-pod

or 
	 
	 kubectl delete -f pod.yaml

Delete cluster
   
	 kind get clusters
	 
then

	 kind delete cluster
