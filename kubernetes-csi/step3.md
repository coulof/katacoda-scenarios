In this step we will enable the CSI flags on the master related components

## Configure k8s master components
The master services are composed of 3 containers, the API server, the scheduler, the Controller Manager
### API server

`diff kube-apiserver.yaml /etc/kubernetes/manifests/kube-apiserver.yaml`{{execute}}


`cp kube-apiserver.yaml /etc/kubernetes/manifests/kube-apiserver.yaml`{{execute}}

### Controller Manager

`cp kube-controller-manager.yaml /etc/kubernetes/manifests/kube-controller-manager.yaml`{{execute}}

### Scheduler

`cp kube-scheduler.yaml /etc/kubernetes/manifests/kube-scheduler.yaml`{{execute}}

## Reload / restart services
Once these files and the ones from previous steps are modify we can reload/restart kubernetes components

```
systemctl daemon-reload
systemctl restart docker
systemctl restart kubelet
```{{execute}}