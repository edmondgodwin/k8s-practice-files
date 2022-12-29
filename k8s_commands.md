#### K8S COMMANDS

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
kubectl delete pod <pod-name>
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
kubectl get pods -o wide
kubectl get po <pod-name> -o yaml 
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
    kubectl apply -f <filename> -n <namespace>

#### kubectl get commands

    kubectl get pod
    kubectl get pod --watch
    kubectl get pod -o wide
    kubectl get service
    kubectl get secret
    kubectl get all | grep mongodb
    kubectl get po -n <namespace>

#### kubectl debugging commands

    watch kubectl get po
    kubectl describe pod mongodb-deployment-xxxxxx
    kubectl describe service mongodb-service
    kubectl logs mongo-express-xxxxxx
    kubectl exec -it po <pod-name> bash   -> used to login to container for debugging
    kubectl exec -it po -c <pod-name> bash   -> used to login to podd with multiple containers
    kubectl edit po <pod-name>   -> used to edit pod manifest if you dont have access to manifest file ** This is a bad idea **

#### give a URL to external service in minikube
```
minikube service mongo-express-service
```

#### Common kubernetes help commands
```
kubectl explain <object_name>
kubectl api-resources
kubectl explain pod.spec
kubectl config -h
```

#### Kubectl Admin commands
```
kubectl label nodes node_name size=medium
kubectl taint nodes <node_name> key1:value1:noSchedule
kubectl taint nodes <node_name> key1:value1:noSchedule- (remove taint on node)
kubectl get taint
kubectl create ns <namespace_name>
kubectl config set-context --current --namespace=<namespace>  (set current namespace to default)
kubectl get quota  (view namespace quota)
kubectl get limitrange
kubectl describe limitrange <limitrange-name>
export KUBECONFIG=/Users/mac/.kube/config
export KUBECONFIG=/Users/mac/kubeconf/aks.conf
```

#### AKS Commands
```
az aks get-credentials --resource-group aks-rg --name aksdemo1

az aks stop --name aksdemo1 --resource-group aks-rg

az aks start --name aksdemo1 --resource-group aks-rg

az aks nodepool scale --name agentpool --cluster-name aksdemo1 --resource-group aks-rg  --node-count 0

az aks show --name aksdemo1 --resource-group aks-rg

```

#### AKS Demo
```
kubeadm join 192.168.15.100:6443 --token gzsbei.whkb2s4n54ytb0i1 \
        --discovery-token-ca-cert-hash sha256:89863f09e894f81ae2e5918eda71da233e6b3669cd9233142f85029d117ab13c 
```
