# echo-server
An example deployment of [echo-server](https://github.com/jmalloc/echo-server).

To deploy run 
```bash
kubectl apply -f -n echo echo-server.yaml
``` 

No ingress controller is assumed to be present at this point, so to reach the echo server we need to forward the port of the pod.
```bash
kubectl port-forward -n echo <echo-server-pod> 8080
```
