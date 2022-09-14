## setup
Install required applications and components by running
```bash
/usr/bin/ansible-playbook \
    -u ubuntu -k -b -K \
    -i '192.168.88.232,192.168.88.233,192.168.88.234,192.168.88.235,' \
    cluster/setup/setup.yml
```

Enabling necessary cgroup resources for `kubeadm` could need some machine specific configurations. 
For Ubuntu 20.04.5 LTS running on Raspberry Pi 4 this meant adding `cgroup_enable=cpuset cgroup_enable=memory cgroup_memory=1` to the end of `/boot/firmware/cmdline.txt`
