Kubernetes Container Storage Interface is GA since version 1.13.

## Check the cluster health is running before moving to the next step
Before moving to the next step we must wait for kubernetes to be fully started
```
watch minikube status
```{{execute interrupt}}

Once all components are started hit <kbd>Ctrl</kbd>+<kbd>C</kbd>

We can check the version is 1.13 or greater
```
kubectl version --short
kubectl cluster-info
```{{execute}}