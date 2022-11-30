# office-kube
Instructions and playbooks for setting up a k8s cluster

- [cluster](./cluster): everything needed for the cluster itself
- [storage](./storage): components for local storage class and nfs storage with a provisioner
- [metallb](./metallb): network load balancer configuration for the bare metal cluster
- [ingress-nginx](./ingress-nginx): ingress controller requiring the metal lb layer2 configuration
- [echo](./echo): a dummy echo service deployment for demo purposes
