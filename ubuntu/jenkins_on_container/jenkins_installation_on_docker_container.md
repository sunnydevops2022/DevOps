# JENKINS INSTALLATION ON DOCKER CONTAINER


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`

## Prerequisite
- Install Docker => https://www.youtube.com/watch?v=G7HgR_2Onks

<br/>

### STEP 1
####  Check Docker service status
```
systemctl status docker
```

<br/>

### STEP 2
#### Check docker version

```
docker version
docker --version
```

<br/>

### STEP 3
#### Check any docker container or images exist or not
```
docker container ls
docker image ls
```

<br/>

### STEP 4
#### Create a directory & change permission of that directory
```
mkdir my_jenkins
chmod -R 777 my_jenkins/
ls -ld my_jenkins/
```

<br/>

### STEP 5
#### Finally will run jenkins on docker container
```
docker run -itd -p 8080:8080 -p 50000:50000 -v /root/my_jenkins:/var/jenkins_home jenkins/jenkins:lts-jdk11

docker container ls
```

<br/>

### STEP 6
#### Now we'll try to open jenkins dashboard from browser
```
http:[server_ip_add:8080]

NOTE: Open port 8080 in security group 
```

<br/>

### STEP 7
#### Get password from jenkins container 
```
docker exec -it bda3398d0842 /bin/bash
cat /var/jenkins_home/secrets/initialAdminPassword
```


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`


We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`

