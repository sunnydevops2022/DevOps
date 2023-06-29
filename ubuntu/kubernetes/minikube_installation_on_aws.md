<h1 align="center">🔥 MINIKUBE INSTALLATION ON UBUNTU 🔥</h1>

<h2 align="center">🔥🔥 👉 Please Like & Subscribe My Channel To Motivate Me 🔥🔥 🙏 👍</h2>

<br/>

#### What you’ll need (Prerequisite)
```
- 2 CPUs or more
- 2 GB of free memory
- 20 GB of free disk space
- Internet connection

NOTE : "t3.small" perfect suit for this lab
```

<br/>

## 🔹STEP-1
#### Change hostname
```
$ whoami
$ sudo hostnamectl set-hostname minikube
$ bash
$ hostname
```

<br/>

## 🔹STEP-2
#### Update Ubuntu packages install required package for this lab
```
$ sudo apt-get update -y
$ sudo apt-get install apt-transport-https curl conntrack
```

<br/>

## 🔹STEP-3
#### Install Docker
```
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
$ ls -l /var/run/docker.sock
$ id
$ sudo usermod -aG docker $USER && newgrp docker
$ id
$ docker --version
```

<br/>

## 🔹STEP-4
#### Install Kubectl
```
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl &&   chmod +x ./kubectl && sudo mv ./kubectl /usr/local/bin/kubectl

$ sudo chmod +x /usr/local/bin/kubectl
$ ls -l /usr/local/bin/kubectl
$ kubectl version --short
```

<br/>

## 🔹STEP-5
#### Install Minikube
```
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ ls -l 
$ sudo install minikube-linux-amd64 /usr/local/bin/minikube
$ minikube version
```

<br/>

## 🔹STEP-6
#### Start Minikube
```
$ kubectl cluster-info
$ minikube start

$ kubectl cluster-info
```

<br/>

## 🔹STEP-7
#### Check Minikube status
```
$ minikube status
$ kubectl get nodes
```

<br/>

## 🔹STEP-8
#### Check Minikube all component status
```
$ kubectl get po -A
```

<br/>

## 🔹STEP-9
#### Create Nginx pod to validate our 1 node minikube cluster
```
$ vim pod.yml
```

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

<br/>

## 🔹STEP-10
#### Run & check Nginx Pod status
```
$ kubectl apply -f pod.yml
$ kubectl get po
```

<br/>

## 🔹STEP-11
#### Delete minikube cluster
```
$ minikube delete --all
```

## 🔥🔥 👉 Please Like & Subscribe My Channel To Motivate Me 🔥🔥 🙏 👍

You will get all steps github repo link in the description box & you will get important video's link related to DevOps.

👉 We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`
