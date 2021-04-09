## Start app 

```
minikube start
kubectl create -f voting-app-pod.yaml
kubectl create -f voting-app-service.yaml
```

Now check the status of app. To check status of pod and service both run 

```
kubectl get pods,svc # if something not ready run this comand again
```
also 
```
minikube service voting-service --url
```

Open url and check the app 

```
kubectl create -f redis-pod.yaml
kubectl create -f redis-service.yaml 
```

and 


```
kubectl create -f postgres-pod.yaml
kubectl create -f postgres-service.yaml 
```

and 

```
kubectl create -f postgres-pod.yaml
kubectl create -f postgres-service.yaml 
```

and 

```
kubectl create -f worker-app-pod.yaml
```
and 

```
kubectl create -f result-app-pod.yaml
kubectl create -f result-app-service.yaml
```

get urls
```
 minikube service result-app-service  --url
 minikube service voting-service --url
 ```