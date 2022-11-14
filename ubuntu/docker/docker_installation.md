# DOCKER INSTALLATION ON UBUNTU


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`


#### Install Docker

```
$ sudo -i
$ sudo apt update
$ sudo apt install apt-transport-https curl gnupg-agent ca-certificates software-properties-common -y
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
$ sudo apt install docker-ce docker-ce-cli containerd.io -y
$ ls -l
$ docker version
$ docker --version
$ sudo systemctl start docker
$ sudo systemctl enable docker
$ sudo systemctl status docker
$ docker ps
$ docker version
$ docker --version
$ docker container ls
$ docker image ls
$ docker run -itd hello-world
$ docker container ls
$ docker container ls -a
$ docker run -itd httpd
$ docker container ls
$ docker image ls
$ docker container ls
```


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`
  

We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`

