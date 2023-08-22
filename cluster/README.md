## setup
Install required applications and components by running
```bash
/usr/bin/ansible-playbook \
    -k -b -K \
    -i cluster/hosts \
    cluster/setup/setup.yml
```

Enabling necessary cgroup resources for `kubeadm init` preflight checks could need some machine specific configurations. 
For Ubuntu 20.04.5 LTS running on Raspberry Pi 4 this meant adding `cgroup_enable=cpuset cgroup_enable=memory cgroup_memory=1` to the end of `/boot/firmware/cmdline.txt`

## destroy
Destroy the kubernetes cluster and remove prerequisites by running
```bash
/usr/bin/ansible-playbook \
    -k -b -K \
    -i cluster/hosts \
    cluster/destroy/destroy.yml
```

### using kubectl
To use kubectl from your local machine at this point, the cluster admin configuration from the control-plane node is needed.
```bash
scp ubuntu@192.168.88.232:/home/ubuntu/.kube/config ~/.kube/office-kube-config
```
Then you can run kubectl commands while specifying the correct config, e.g.
```bash
kubectl --kubeconfig ~/.kube/office-kube-config get nodes
```

Or the new config can be merged with an existing one, if you have already been using kubectl:
Make a copy of your existing config
```bash 
cp ~/.kube/config ~/.kube/config.bak
```
Merge the two config files together into a new config file 
```bash
KUBECONFIG=~/.kube/config:~/.kube/office-kube-config kubectl config view --flatten > new-config
```
Replace your old config with the new merged config 
```bash
mv new-config ~/.kube/config 
```
