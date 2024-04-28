<h2 align="center">🔥🔥 👉 Please Like & Subscribe My Channel To Motivate Me 🔥🔥 🙏 👍</h2>

<h3 align="left">Connect with me:</h3>
<p align="left">

- Click 👉 **[Whatsapp DevOps Jobs Group](https://chat.whatsapp.com/J1oriqe9ckc9NolOiStPti)**
- Click 👉 **[Telegram DevOps Jobs Group](https://t.me/DevOps_Linux_Jobs)**
- Click 👉 **[YouTube](https://www.youtube.com/@sunnygodiwal007/)**
- Click 👉 **[GitHub](https://github.com/sunnydevops2022/)**
- Click 👉 **[LinkedIn](https://www.linkedin.com/in/sunnygodiwal/)**

<br/>

<h1 align="center">🔥 DOCKER INSTALLATION ON UBUNTU  (AWS) 🔥</h1>

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

<h2 align="center">🔥🔥 👉 Please Like & Subscribe My Channel To Motivate Me 🔥🔥 🙏 👍</h2>

You will get all steps github repo link in the description box.

We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`

