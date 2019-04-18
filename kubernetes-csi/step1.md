Kubernetes Container Storage Interface is GA since version 1.13.

## Start kubernetes with minikube
Before moving to the next step we must wait for kubernetes to be fully started
```
minikube start \
    --network-plugin=cni \
    --enable-default-cni
```{{execute}}


We can check the version is 1.13 or greater
```
kubectl version --short
kubectl cluster-info
```{{execute}}