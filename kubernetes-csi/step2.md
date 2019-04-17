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
`diff /etc/systemd/system/kubelet.service.d/10-kubeadm.conf 10-kubeadm.conf.patch`{{execute}}

Let's patch the service
`cp 10-kubeadm.conf /etc/systemd/system/kubelet.service.d/10-kubeadm.conf`{{execute}}

## Update docker

`diff docker.service /lib/systemd/system/docker.service`{{execute}}

`cp docker.service /lib/systemd/system/docker.service`{{execute}}