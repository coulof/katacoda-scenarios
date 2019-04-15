In this step we will enable the CSI flags

## Update kubelet configuration
On master :
```
echo "VolumeSnapshotDataSource: true
KubeletPluginsWatcher: true
CSINodeInfo: true
CSIDriverRegistry: true
BlockVolume: true
CSIBlockVolume: true" >> /var/lib/kubelet/config.yaml
```{{execute HOST1}}

On minion:
```
echo "VolumeSnapshotDataSource: true
KubeletPluginsWatcher: true
CSINodeInfo: true
CSIDriverRegistry: true
BlockVolume: true
CSIBlockVolume: true" >> /var/lib/kubelet/config.yaml
```{{execute HOST2}}


## Update kubelet service
On startup of kubelet service we also need to set the CSI flags

`patch /etc/systemd/system/kubelet.service.d/10-kubeadm.conf 10-kubeadm.conf.patch`{{execute HOST1}}

`patch /etc/systemd/system/kubelet.service.d/10-kubeadm.conf 10-kubeadm.conf.patch`{{execute HOST2}}
