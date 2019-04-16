In this step we will enable the CSI flags.
These steps have to be done on EVERY nodes of your cluster (master and workers)

## Update kubelet configuration

```
echo "VolumeSnapshotDataSource: true
KubeletPluginsWatcher: true
CSINodeInfo: true
CSIDriverRegistry: true
BlockVolume: true
CSIBlockVolume: true" >> /var/lib/kubelet/config.yaml
```{{execute}}

## Update kubelet service
On startup of kubelet service we also need to set the CSI flags
`cat 10-kubeadm.conf.patch`{{execute}}

Let's patch the service
`patch /etc/systemd/system/kubelet.service.d/10-kubeadm.conf 10-kubeadm.conf.patch`{{execute}}

## Update docker

`cat docker.service.patch`{{execute}}

`patch /lib/systemd/system/docker.service docker.service.patch`{{execute}}