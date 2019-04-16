In this step we will enable the CSI flags

## Configure k8s master components
### API server
`cat kube-apiserver.yaml.patch`{{execute}}

`patch /etc/kubernetes/manifests/kube-apiserver.yaml kube-apiserver.yaml.patch`{{execute}}
### Controller Manager

`patch /etc/kubernetes/manifests/kube-controller-manager.yaml kube-controller-manager.yaml.patch`{{execute}}

### Scheduler

`patch /etc/kubernetes/manifests/kube-scheduler.yaml kube-scheduler.yaml.patch`{{execute}}

## Reload / restart services
```
systemctl daemon-reload
systemctl restart docker
systemctl restart kubelet
```{{execute}}