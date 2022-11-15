# DOCKER INSTALLATION ON UBUNTU  (AWS)


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`


#### Install Docker

```
$ sudo -i
$ sudo apt-get remove docker docker-engine docker.io containerd runc
$ sudo apt-get update
$ sudo apt-get install     ca-certificates     curl     gnupg     lsb-release
$ sudo mkdir -p /etc/apt/keyrings
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
$ echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
$ sudo docker run hello-world
$ docker --versino
$ docker version
$ docker --version
$ docker container ls
$ docker image ls
$ mkdir my_jenkins
$ chmod -R 777 my_jenkins/
$ ls -l my_jenkins/
$ docker run -itd -p 8080:8080 -p 50000:50000 -v /root/my_jenkins:/var/jenkins_home jenkins/jenkins:lts-jdk11
$ docker container ls
$ docker exec -it bda3398d0842 /bin/bash

jenkins@bda3398d0842:/$ cat /var/jenkins_home/secrets/initialAdminPassword
4d6c5e6995c34dbdae2ccbffd17c04a3
jenkins@bda3398d0842:/$
```


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`
  

We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`

