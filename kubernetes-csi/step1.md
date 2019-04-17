Kubernetes Container Storage Interface is GA since version 1.13.

## Check the cluster is running before moving to the next step
```
until $(minikube status); do
  if [ echo $ -ne 0 ]; then
     minikube status
     echo "starting..."
     sleep 2
  fi
done
```{{execute}}

```
kubectl version --short
kubectl cluster-info
`{{execute}}