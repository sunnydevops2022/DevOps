## KUBERNETES CLUSTER INSTALLATION

# Pre-Requisites

### Kubernetes Cluster Server Details:
```
Operating System     : Ubuntu 18.04/20.04 LTS		 # master-node
Hostname             : master-node
IP Address           : 192.168.0.50/24
RAM                  : 2 GB
CPU                  : 2 Core
EC2 Instance         : t3a.small
```

#### Update repository of ubuntu
```
sudo apt update
```

### Change time zone
```
date
timedatectl
sudo timedatectl set-timezone Asia/Kolkata
timedatectl
date
```

### Change time hostname
```
hostnamectl set-hostname k8-master
bash
```

### Install Java
```
Pending        
```

# SETTING UP KUBERNETES CLUSTER SERVER ON AWS WITH Ubuntu 18.04/20.04 LTS STEP BY STEP !!!
```
Last Tested Date : 24-Apr-2023
```

# ON MASTER NODE

### Switch to root user
```
sudo -i

$ cat /etc/os-release
NAME="Ubuntu"
VERSION="20.04.5 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.5 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal
```

### Start by disabling the swap memory
```
sudo swapoff -a
sed -i 's/^\(.*swap.*\)$/#\1/' /etc/fstab
```



### Set Hostname
```
sudo hostnamectl set-hostname master-node

bash
```



### Update the package list with the command:
```
sudo apt-get update
```



### Next, install Docker with the command:
```
sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```    

### Add Docker’s official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -	
```


### Add Docker Repo
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```   

### Install the latest version of Docker Engine and containerd
```
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
```


### Check the installation (and version) by entering the following:
```
docker version
```


### The product_uuid can be checked by using the command
``` 
sudo cat /sys/class/dmi/id/product_uuid
```


### Set Docker to launch at boot by entering the following:
```
sudo systemctl enable docker
```


### Verify Docker is running:
```
sudo systemctl status docker
```


### Add Kubernetes Repo
```
{
  curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
  echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" > /etc/apt/sources.list.d/kubernetes.list
}
```

### Install kubeadm kubelet kubectl
```
apt update && apt install -y kubeadm=1.18.5-00 kubelet=1.18.5-00 kubectl=1.18.5-00         ## For 1.18 version
OR
apt update && apt-get install -y kubelet=1.21* kubeadm=1.21* kubectl=1.21*                 ## For 1.21 version


sudo apt-mark hold kubelet kubeadm kubectl
```

### Verify the installation with:
```
kubeadm version
kubectl version --short
```

### Initialize Kubernetes on Master Node
```
sudo kubeadm init --pod-network-cidr=10.244.0.0/16
```

### Enter the following to create a directory for the cluster: To start using your cluster, you need to run the following as a regular user:
```
sudo mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```


### Now check to see if the kubectl command is activated.
```
kubectl get nodes								//Status of Nodes

root@master-node:~# kubectl get nodes
NAME          STATUS   ROLES    AGE    VERSION
master-node   NOtReady    master   8m3s   v1.18.5
root@master-node:~#

# Deploy Pod Network to Cluster
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml

# Verify that everything is running and communicating:

root@master-node:~# kubectl get pods --all-namespaces     //Status of PODS
NAMESPACE      NAME                                  READY   STATUS    RESTARTS   AGE
kube-flannel   kube-flannel-ds-6slf4                 1/1     Running   1          8m44s
kube-system    coredns-66bff467f8-bzr6k              1/1     Running   1          8m55s
kube-system    coredns-66bff467f8-r5jbq              1/1     Running   1          8m55s
kube-system    etcd-master-node                      1/1     Running   1          9m10s
kube-system    kube-apiserver-master-node            1/1     Running   1          9m10s
kube-system    kube-controller-manager-master-node   1/1     Running   1          9m9s
kube-system    kube-proxy-smh7n                      1/1     Running   1          8m55s
kube-system    kube-scheduler-master-node            1/1     Running   1          9m10s
root@master-node:~#

kubectl get -o wide pods --all-namespaces 		//Detailed status of PODS

# Kubernetes Bash Completion
cd ~										 //Change directory to user home
cd .kube   							    	 //.kube folder should be exist
kubectl completion bash > <filename.sh>      //
source $HOME/.kube/<filename.sh>			 //after system restart it won't work
```


### Install nfs utils for Kubernetes NFS driver
```
yum -y install nfs-utils
```
</br>

# ON WORKER NODE

### Start by disabling the swap memory
```
sudo swapoff -a
sed -i 's/^\(.*swap.*\)$/#\1/' /etc/fstab 
```

### Set Hostname
```
sudo hostnamectl set-hostname worker1

bash
```

### Update the package list with the command:
```
sudo apt-get update
```

### Next, install Docker with the command:
```
sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```    

### Add Docker’s official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### Add Docker Repo
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

### Install the latest version of Docker Engine and containerd
```
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
```

### Check the installation (and version) by entering the following:
```
docker version
```

### The product_uuid can be checked by using the command 
```
sudo cat /sys/class/dmi/id/product_uuid
```


### The product_uuid can be checked by using the command
``` 
sudo cat /sys/class/dmi/id/product_uuid
```


### Set Docker to launch at boot by entering the following:
```
sudo systemctl enable docker
```


### Verify Docker is running:
```
sudo systemctl status docker
```


### Add Kubernetes Repo
```
{
  curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
  echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" > /etc/apt/sources.list.d/kubernetes.list
}
```

### Install kubeadm kubelet kubectl
```
apt update && apt install -y kubeadm=1.18.5-00 kubelet=1.18.5-00 kubectl=1.18.5-00         ## For 1.18 version
OR
apt update && apt-get install -y kubelet=1.21* kubeadm=1.21* kubectl=1.21*                 ## For 1.21 version


sudo apt-mark hold kubelet kubeadm kubectl
```

### Verify the installation with:
```
kubeadm version
kubectl version --short
```


### Join Worker Node to Cluster
```
kubeadm join 192.168.0.50:6443 --token we46ga.428vdjjol7uci4nt \
    --discovery-token-ca-cert-hash sha256:ede9e9fcde60df98417559cfd1cb0e653dea84a29fa747d7260f0c04d36b61d5           ###  This Sunny Token
```

### Nfs Client package need to install all worker node for Nfs mount volumes
```
sudo apt install nfs-common
```

<br/>

# KUBERNETES CLUSTER TESTING
cat testing.yaml
```
apiVersion: v1
kind: Pod
metadata:
  name: testing
spec:
  containers:
  - name: testing
    image: nginx
```

# NGINX CONTROLLER  (Pending)

Installation: https://docs.nginx.com/nginx-ingress-controller/installation/installation-with-manifests/

Version : https://docs.nginx.com/nginx-ingress-controller/technical-specifications/

Testing : git clone https://github.com/nginxinc/kubernetes-ingress.git --branch release-1.12


another url : https://www.devopsschool.com/tutorial/kubernetes/kubernetes-ingress-tutorial.html


Extra
-----
kubectl patch svc nginx-ingress -n nginx-ingress -p '{"spec":{"externalIPs":["<ec2-master-pub-ip>"]}}'

Eg:
kubectl patch svc nginx-ingress -n nginx-ingress -p '{"spec":{"externalIPs":["3.82.109.3"]}}'



Kubernetes Ingress Tutorial | Ingress Vs Service, Install Nginx Ingress | Kubernetes Tutorial Part 9
youtube: https://www.youtube.com/watch?v=11SqM8YvcYE



Delete Stuck Namespace
----------------------
NS=`kubectl get ns |grep Terminating | awk 'NR==1 {print $1}'` && kubectl get namespace "$NS" -o json   | tr -d "\n" | sed "s/\"finalizers\": \[[^]]\+\]/\"finalizers\": []/"   | kubectl replace --raw /api/v1/namespaces/$NS/finalize -f -


Delete Stuck pod
----------------------
kubectl delete pods --grace-period=0 --force <pod_name> -n <namespace>


## `*************************   EOF   *************************`
