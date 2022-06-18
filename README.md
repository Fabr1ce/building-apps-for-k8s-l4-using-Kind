# building-apps-for-k8s-l4

This repository is used to build a k8's cluster locally for testing before deployment.

First kind is used to spin up a k8's cluster, minikube or docker desktop can also be used here:
  kind create cluster
The created cluster is verified using the following cmds:
  kind get clusters which return the name of the cluster (kind)
  kubectl cluster-info returns the k8's master and kubeDNS info
  kubectl config get-contexts returns inactive and active contexts (kind-kind)
  kubectl get nodes returns the kube-control-plane
  kubectl get all -A returns all the nodes spun up by kind to launch the k8's cluster
