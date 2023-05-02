## JENKINS INSTALLATION

#### Update repository of ubuntu
```
sudo apt update
```

### Change time zone
```
date
vim .profile

# Add end of the file
TZ='Asia/Kolkata'; export TZ

source .profile
bash
date
```

### Change time hostname
```
hostnamectl set-hostname jenkins-ansible
bash
```

### Install Java
```
java -version
apt-get install openjdk-17-jdk -y       ## For sonarqube-10.0.0.68432.zip
apt-get install openjdk-11-jdk -y       ## For sonarqube-8.9.2.46101.zip
java -version         
```

### Install Jenkins
```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
sudo apt-get update
sudo apt-get install jenkins
```

### Service start
```
systemctl start jenkins
```

### Service enable & check status
```
systemctl enable jenkins
systemctl status jenkins
```

### check 8080 port is used or not
```
netstat -plant | grep 8080
```

### Open jenkins on browser
```
URL:   http://<jenkins_server_ip>:8080
```

<br/>
<br/>
<br/>
<br/>

## ++++++++++++++++++ ANSIBLE ++++++++++++++++++



## `*************************   EOF   *************************`