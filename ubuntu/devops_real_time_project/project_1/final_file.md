# +++++ Project-1 +++++

#### `**** Please Like & Subscribe My Channel To Motivate Me ****`

#### Via Root user
```
$ sudo -i
$ adduser devops-user
$ vim /etc/sudoers
$ vim /etc/ssh/sshd_config
$ systemctl restart sshd
$ su - devops-user
```

<br />

#### Update Ubuntu packages
```
$ whoami
$ sudo apt-get update
```

<br />

#### Change hostname
```
$ sudo hostnamectl set-hostname ansible
$ bash
$ hostname
```

<br />

#### Add Ansible repository
```
$ sudo apt-add-repository ppa:ansible/ansible
```

<br />

#### Now fetch latest update & install Ansible
```
$ sudo apt update
$ sudo apt-get install ansible
```

<br />

#### Now check Ansible version
```
$ ansible --version
```


#### Docker installation on Ansible Uninstall old versions

```
$ sudo apt-get remove docker docker-engine docker.io containerd runc
```

<br/>

#### Set up the repository
```
$ sudo apt-get update
$ sudo apt-get install ca-certificates curl gnupg lsb-release net-tools
```

<br/>

#### Add Docker’s official GPG key
```
$ sudo mkdir -p /etc/apt/keyrings

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
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
$ sudo apt-get update

$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

<br/>

#### Start Docker service
```
$ sudo systemctl start docker

$ sudo systemctl enable docker

$ sudo systemctl status docker
```

<br/>

#### Check docker version

```
docker version

docker --version
```

<br/>

#### Ch
```
id
cat /etc/group | grep docker
sudo usermod -aG docker ${USER}
$ sudo reboot
id
docker login

$ sudo mkdir -p /opt/playbooks
$ sudo mkdir -p /opt/docker
$ ls -l /opt/

$ sudo chown -R devops-user:devops-user /opt/docker
$ sudo chown -R devops-user:devops-user /opt/playbooks
$ ls -l /opt/
```




















# +++++ DOCKER INSTALLATION +++++

#### Via Root user
```
$ sudo -i
$ adduser devops-user
$ vim /etc/sudoers
$ vim /etc/ssh/sshd_config
$ systemctl restart sshd
$ su - devops-user
```

<br />

#### Update Ubuntu packages
```
$ whoami
$ sudo apt-get update
```

<br />

#### Change hostname
```
$ sudo hostnamectl set-hostname docker
$ bash
$ hostname
```

#### Docker installation on Ansible Uninstall old versions

```
$ sudo apt-get remove docker docker-engine docker.io containerd runc
```

<br/>

#### Set up the repository
```
$ sudo apt-get update

$ sudo apt-get install ca-certificates curl gnupg lsb-release net-tools
```

<br/>

#### Add Docker’s official GPG key
```
$ sudo mkdir -p /etc/apt/keyrings

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
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
$ sudo apt-get update

$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

<br/>

#### Start Docker service
```
$ sudo systemctl start docker

$ sudo systemctl enable docker

$ sudo systemctl status docker
```

<br/>

#### Check docker version

```
$ docker --version
```


```
id
cat /etc/group | grep docker
sudo usermod -aG docker ${USER}
$ sudo reboot
id
docker login

```


# Swich to Anisble server & Integrate with Docker server

#### passwordless authentication from ansitble to docker server

```
$ hostname
$ ssh 172.31.28.54                         ## Docker_private_ip_address
$ ssh-keygen
$ ls -l .ssh/
$ ssh-copy-id devops-user@172.31.28.54     ## Docker_private_ip_address
$ ssh 172.31.28.54                         ## Docker_private_ip_address
```


#### Check ansible able to connect with ping pong
```
$ ansible -m ping all
$ sudo vim /etc/ansible/hosts
$ ansible -m ping all

```

#### Create yml file
```
$ cd /opt/playbooks/
$ vim create_docker_container.yml
```

```
---
- hosts: all
  become: true
  tasks: 
    - name: Create Docker Container
      shell: docker run -itd --name webapp -p 8090:8080 sunnydevops2022/test:latest
```

```
cd /opt/docker
docker build -t $JOB_NAME:v1.$BUILD_ID
docker tag $JOB_NAME:v1.$BUILD_ID sunnydevops2022/$JOB_NAME.v1.$BUILD_ID
docker tag $JOB_NAME:v1.$BUILD_ID sunnydevops2022/$JOB_NAME:latest
docker push sunnydevops2022/$JOB_NAME:v1.$BUILD_ID
docker push sunnydevops2022/$JOB_NAME:latest
docker rmi $JOB_NAME:v1.$BUILD_ID sunnydevops2022/$JOB_NAME:v1.$BUILD_ID sunnydevops2022/$JOB_NAME:latest
```















# Swich to Jenkins server & Integrate with Ansbile server
```
manage plugins > available > Publish Over SSH > Downlaod now and install after restart

manage jenkins > Configure system > Publish Over SSH > 
                                                    Add >
                                                        Name : Ansible-Server
                                                        Hostname : 172.31.24.20  (Ansible_Private_IP)
                                                        Username : devops-user
                                                        Use password authentication, or use a different key : password
                                                    
                                                    Test configurations
                                                    Apply & Save 
```

#### sdf
```
go to job > Post-build Actions > send build artifact over ssh > 

```
```
cd /opt/playbooks
ansible-playbook create_docker_container.yml
```



#### Github Webhook integration with Jenkins
```
Repo Settings > Webhooks > Add Webhook > 
                              Payload URL  : http://<jenkins_public_ip>:<8080>/github-webhook/
                              Content type : application/json
                              Secret       : blank
                              Event        : Just the Push Event
                          
                          click on the “Add Webhook”


Jenkins Dashboard > Job_Name > Build Triggers > Build Triggers > GitHub hook trigger for GITScm polling > Apply & Save
```


#### Email Integration Jenkins
```
Email Integration
```

#### `**** Please Like & Subscribe My Channel To Motivate Me ****`

You will get all steps github repo link in the description box.

We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`


```
---
- hosts: all
  become: true
  tasks:
    - name: Stop Previous Version Docker
      shell: docker stop webapp

    - name: Remove stopped webapp container
      shell: docker rm -f webapp 

    - name: Remove Docker Images
      shell: docker image rm -f sunnydevops2022/test:latest
    
    - name: Create Docker Container
      shell: docker run -itd --name webapp -p 8080:8080 sunnydevops2022/test:latest
```
