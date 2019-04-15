In this step we will enable the CSI flags

## Configure k8s master components
### API server
### Controller Manager
### Scheduler

## Reload / restart services
```
systemctl daemon-reload
systemctl restart docker
systemctl restart kubelet
```