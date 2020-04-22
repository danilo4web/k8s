# Kubernetes

#### install kubectl
```
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
$ chmod +x ./kubectl
$ sudo mv ./kubectl /usr/local/bin/kubectl
```

#### install minikube
```
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ chmod +x ./minikube
$ sudo mv ./minikube /usr/local/bin/minikube
```

#### Minikube start
```
$ minikube start
$ minikube dashboard
```

#### Deployment
```
$ kubectl create -f deployment.yml
```

#### GET
```
$ kubectl get pods
$ kubectl get services
$ kubectl get deployments
 ```

#### Delete Deployment
```
$ kubectl delete pods nginx
$ kubectl delete services nginx
$ kubectl delete deployments nginx
```

#### Scale:
```
$ kubectl scale deployment --replicas=10 hello-world-deployment
$ kubectl get deploy
$ kubectl get pods -w
```
