## Start app 

### Deploying using pods

``` bash
minikube start
kubectl create -f voting-app-pod.yaml
kubectl create -f voting-app-service.yaml
```

Now check the status of app. To check status of pod and service both run 

``` bash
kubectl get pods,svc # if something not ready run this comand again
```

also 

```bash
minikube service voting-service --url
```

Open url and check the app 

```bash
kubectl create -f redis-pod.yaml
kubectl create -f redis-service.yaml 
```

and 


```bash
kubectl create -f postgres-pod.yaml
kubectl create -f postgres-service.yaml 
```

and 

```bash
kubectl create -f postgres-pod.yaml
kubectl create -f postgres-service.yaml 
```

and 

```bash
kubectl create -f worker-app-pod.yaml
```
and 

```bash
kubectl create -f result-app-pod.yaml
kubectl create -f result-app-service.yaml
```

get urls

```bash
 minikube service result-app-service  --url
 minikube service voting-service --url
```

It is not good way as if you want to update your app then you have to respawn your app image which can cause downtime so to handle that

## To create deployment

```bash
kubectl create -f voting-app-deployment.yaml 
kubectl create -f voting-app-service.yaml
```

Check if app is runnig 

```bash
kubectl get deployment
```

```bash
kubectl create -f redis-deployment.yaml 
kubectl create -f redis-service.yaml
kubectl create -f postgres-deployment.yaml 
kubectl create -f postgres-service.yaml 
kubectl create -f worker-app-deployment.yaml 
```

To scale replicas 
```bash
kubectl scale deployment voting-app-deployment --replicas=3
```
Now if we refresh voting app we can see that containerId is diff on refresh which means it is using replicas 

### Why service ?
1. We have created service of apps which we want to access inside the cluster by name of pod
- redis, postgres we want them in worker app
2. We want some pods to be accessible for the outside users for that we will create service of them and set spec type as NodePort