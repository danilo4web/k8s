## Replica Set

##### Intactive playground to learn kubernates 
https://labs.play-with-k8s.com/
*******


#### Create and display replicaset
```
kubectl create -f nginx-rs.yaml
kubectl get po -o wide
kubectl get po -l app=nginx-app
kubectl get rs nginx-rs -o wide
kubectl describe rs nginx-rs
```

#### Automatic Pod Reschedule 
```
kubectl get po -o wide --watch
kubectl get po -o wide
kubectl get nodes
```

#### Scale up pods
```
kubectl scale rs nginx-rs --replicas=5
kubectl get rs nginx-rs -o wide
kubectl get po -o wide
```

#### Scale down pods
```
kubectl scale rs nginx-rs --replicas=3
kubectl get rs nginx-rs -o wide
kubectl get po -o wide
```

#### Cleanup
```
kubectl delete -f nginx-rs.yaml
kubectl get rs
kubectl get po -l app=nginx-app
```
