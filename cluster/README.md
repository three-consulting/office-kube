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
