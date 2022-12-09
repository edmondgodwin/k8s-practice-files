#### K8S COMMANDS###

kubectl create -h (show help for kubectl create)
Usage:

```
kubectl create -f FILENAME [options]
```

**kubectl apply commands in order**

> Examples:

#### Create a deployment named my-dep that runs the busybox image


```
kubectl create deployment my-dep --image=busybox
```

#### Create a deployment with a command
  
```
kubectl create deployment my-dep --image=busybox -- date
```

#### Create a deployment named my-dep that runs the nginx image with 3 replicas
  
```
kubectl create deployment my-dep --image=nginx --replicas=3
```

#### Create a deployment named my-dep that runs the busybox image and expose port 5701

```
kubectl create deployment my-dep --image=busybox --port=5701
```
  
**DELETE DEPLOYMENT**

```
kubectl delete deployment <deployment-name>
```


**CREATE DEPLOYMENT FILE**

```
kubectl apply -f <filename.yaml>
```

  
**GET COMMAND**

```
kubectl get all
kubectl get all | grep <deployment-name>
kubectl get deployment
kubectl get nodes
kubectl get pods
kubectl get pods --watch
kubectl get service
kubectl get replicaset
kb get pods -o wide
```


**EDIT DEPLOYMENT**

```
kubectl edit deployment <dep-name>
```


**DESCRIBE**

```
kubectl describe pod <pod-name>
```


**SSH INTO THE CONTAINER**

```
kubectl exec -it <pod-name> -- bin/bash
```


**CREATING SECRET**

The value pair for the secret must be created with a base 64 encoding

```
echo -n 'enter the value' | base64
```


#### kubectl apply commands in order
    
    kubectl apply -f mongo-secret.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-configmap.yaml 
    kubectl apply -f mongo-express.yaml

#### kubectl get commands

    kubectl get pod
    kubectl get pod --watch
    kubectl get pod -o wide
    kubectl get service
    kubectl get secret
    kubectl get all | grep mongodb

#### kubectl debugging commands

    kubectl describe pod mongodb-deployment-xxxxxx
    kubectl describe service mongodb-service
    kubectl logs mongo-express-xxxxxx

#### give a URL to external service in minikube
```
minikube service mongo-express-service
```

#### Common kubernetes help commands
```
kubectl explain <object_name>
kubectl api-resources
kubectl explain pod.spec
```

