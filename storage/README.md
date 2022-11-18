## storage

To use dynamic storage via NFS, install the [nfs-subdir-external-provisioner](https://github.com/kubernetes-sigs/nfs-subdir-external-provisioner) by
```bash
helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
helm install nfs-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner \
    --namespace nfs-provisioner \
    --create-namespace \
    --version "4.0.17" \
    --values nfs-values.yaml
```

or a local storage class if you want all the hassle
```bash
kubectl apply -f storage-class.yaml
```
