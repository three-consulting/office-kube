## NGINX ingress controller
Install the ingress controller using helm
```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm upgrade ingress-nginx ingress-nginx/ingress-nginx \
    --install \
    --namespace ingress-nginx \
    --create-namespace \
    --version "4.4.0"
```
