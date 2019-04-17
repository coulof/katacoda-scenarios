In this step we will enable the CSI flags on the master related components

## Configure k8s master components
The master services are composed of 3 containers, the API server, the scheduler, the Controller Manager
### API server
`cat kube-apiserver.yaml.patch`{{execute}}

`patch /etc/kubernetes/manifests/kube-apiserver.yaml kube-apiserver.yaml.patch`{{execute}}
### Controller Manager

`patch /etc/kubernetes/manifests/kube-controller-manager.yaml kube-controller-manager.yaml.patch`{{execute}}

### Scheduler

`patch /etc/kubernetes/manifests/kube-scheduler.yaml kube-scheduler.yaml.patch`{{execute}}

## Reload / restart services
Once these files and the ones from previous steps are modify we can reload/restart kubernetes components

```
systemctl daemon-reload
systemctl restart docker
systemctl restart kubelet
```{{execute}}