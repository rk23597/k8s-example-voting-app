### Example Voting App by Docker Hub

This is based on the original [example-voting-app](https://github.com/dockersamples/example-voting-app) from docker-examples(https://github.com/dockersamples) modified to work on Kubernetes   



Execute following com mands on Any Kubernetes cluster available in Public Cloud (like Azure, AWS or GCP etc,). Reason for Public Cloud is we have two services of type Load Balancer, which can't be used on local setup.

Kubernetes Services : Type 
db  : ClusterIP      
redis   : ClusterIP    
result-service  :  LoadBalancer    
voting-service   :  LoadBalancer    

```
kubectl create -f voting-app-pod.yaml 
kubectl create -f voting-app-service.yaml 
kubectl create -f redis-pod.yaml 
kubectl create -f redis-service.yaml 
kubectl create -f postgres-pod.yaml 
 kubectl create -f postgres-service.yaml 
kubectl create -f worker-app-pod.yaml 
kubectl create -f result-app-pod.yaml 
kubectl create -f result-app-service.yaml 
```