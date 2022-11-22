# metal lb
Install [MetalLB](https://metallb.universe.tf/) using the official helm chart
```bash
helm repo add metallb https://metallb.github.io/metallb
helm upgrade metallb metallb/metallb \
    -i \
    --namespace metallb-system \
    --create-namespace \
    --version "0.13.7"
```
Set up layer 2 mode
```bash
kubectl apply -f metallb/layer2.yaml
```
