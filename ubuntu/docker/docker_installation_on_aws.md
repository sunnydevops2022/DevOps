# DOCKER INSTALLATION ON UBUNTU  (AWS)


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`


#### Switch to root user & change hostname
```
sudo -i

hostnamectl set-hostname docker

bash
```

<br/>

#### Uninstall old versions

```
sudo apt-get remove docker docker-engine docker.io containerd runc
```

<br/>

#### Set up the repository
```
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

<br/>

#### Add Docker’s official GPG key
```
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

<br/>

#### Use the following command to set up the repository
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

<br/>

#### Install Docker Engine
```
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

<br/>

#### Start Docker service
```
systemctl start docker

systemctl enable docker

systemctl status docker
```

<br/>

#### Check docker version

```
docker version

docker --version
```

<br/>

#### Run demo sample container
```
docker container ls

docker image ls

docker run -itd httpd

docker container ls

docker image ls
```

#### `**** Please Like & Subscribe My Channel To Motivate Me ****`

You will get all steps github repo link in the description box.

We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`

