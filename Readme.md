# Run 
To run the app use 

```
kubectl apply -f pod.yaml
```

# Explanation 

Must have fields 
- apiVersion 
- kind
- metadata
- spec
  
```
apiVersion: v1 # this is version of kubernetes api you are using to create the object (depend on what you want to create)
kind: Pod # Type of object we want to create 
metadata: 
  name: nginx
  label: 
    app:  nginx
    tier: frontend

spec: 
  containers: # List of images you want to add in pod
  - name: nginx
    image: nginx
```