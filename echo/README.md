# echo-server
An example deployment of [echo-server](https://github.com/jmalloc/echo-server).

To deploy run 
```bash
kubectl apply -n echo -f echo-server.yaml
``` 

No ingress controller is assumed to be present at this point, so to reach the echo server we need to forward the port the service.
```bash
kubectl -n echo port-forward svc/echo-server 8080
```
