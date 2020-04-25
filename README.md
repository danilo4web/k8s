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


## Cluster K8S

#### disabe swap
```
swapoff -a
```

#### install docker
```
sudo apt-get update &&  
sudo apt install docker.io && 
sudo systemctl enable docker.service &&
docker info | grep -i cgroup
```

#### install (kubelet | kubeadm | kubectl)
```
sudo apt-get update
sudo apt-get install -y apt-transport-https && 
sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - && 
sudo echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" > /etc/apt/sources.list.d/kubernetes.list &&
sudo apt-get update &&
sudo apt-get install -y kubelet kubeadm kubectl && 
sudo sed -i "s/cgroup-driver=systemd/cgroup-driver=cgroupfs/g" /etc/systemd/system/kubelet.service.d/10-kubeadm.conf && 
sudo systemctl daemon-reload && 
sudo systemctl restart kubelet
```

#### create master server
```
sudo kubeadm init --v=5 --apiserver-advertise-address $(hostname -i) --ignore-preflight-errors=NumCPU &&
mkdir -p $HOME/.kube &&
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config &&
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

##### *** just run kubeadm join on slave servers


### recovery token
```
kubeadm token create --print-join-command
```
