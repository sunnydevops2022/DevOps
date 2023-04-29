## JENKINS INSTALLATION

#### Update repository of ubuntu
```
Download URL:  https://www.sonarsource.com/products/sonarqube/downloads/

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
hostnamectl set-hostname jenkins
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
Pending
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