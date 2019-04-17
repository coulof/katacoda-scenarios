Now that CSI is enable we can start to use a provider.

In that example we will use (csi driver for host path)[https://github.com/kubernetes-csi/csi-driver-host-path]

## Get the host path provider

```
wget https://github.com/kubernetes-csi/csi-driver-host-path/archive/master.zip
unzip master
```{execute}

```
cd
deploy/kubernetes-1.13/deploy-hostpath.sh
```{execute}

## Ensure the different pods are running

```
kubectl get pods
```{execute}

## Create persistent volumes

```
kubectl create -f ./examples
```{execute}

## Confirm Hostpath driver works
```
kubectl exec -it my-csi-app /bin/sh
```{execute}

```
kubectl exec -it $(kubectl get pods --selector app=csi-hostpathplugin -o jsonpath='{.items[*].metadata.name}') -c hostpath /bin/sh
```{execute}