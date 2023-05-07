## ++++++++++++++++++ JENKINS INSTALLATION ++++++++++++++++++

## Pre-Requisites

### Jenkins Server Details:
```
Operating System     : Ubuntu
Hostname             : jenkins-ansible
RAM                  : 2 GB
CPU                  : 1 Core
EC2 Instance         : t2.small
```

#### Update repository of ubuntu
```
sudo -i
sudo apt-get update
```

### Change time zone
```
date
timedatectl
sudo timedatectl set-timezone Asia/Kolkata
timedatectl
date
```

### Change hostname
```
hostname
hostnamectl set-hostname jenkins-ansible
bash
hostname
```

### Install Java
```
java -version
apt-get install openjdk-11-jdk 
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
sudo apt-get install jenkins=2.361.3 -y
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

### Check 8080 port is used or not
```
netstat -plant | grep 8080
```

### Check version & Open jenkins on browser
```
jenkins --version

URL:   http://<jenkins_server_ip>:8080
```

### Get Jenkins Administrator password using this command
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

<br/>
<br/>
<br/>
<br/>

## ++++++++++++++++++ ANSIBLE INSTALLATION ++++++++++++++++++

### Add Ansible repository
```
sudo apt-add-repository ppa:ansible/ansible
```

### Now fetch latest update & install Ansible
```
sudo apt update
sudo apt-get install ansible -y
```

### Now check Ansible version
```
ansible --version
```

<br/>
<br/>
<br/>
<br/>

## ++++++++++++++++++ MAVEN INSTALLATION ++++++++++++++++++

### Check version before install
```
mvn --version
```

### Change dir to /opt and download maven
```
cd /opt/
ls
wget https://dlcdn.apache.org/maven/maven-3/3.9.1/binaries/apache-maven-3.9.1-bin.zip
apt-get install unzip -y
unzip apache-maven-3.9.1-bin.zip
ls
rm -rf apache-maven-3.9.1-bin.zip
ls
```

### Configure maven home path
```
vim ~/.bashrc

## Add end of the file & save it.
export M2_HOME=/opt/apache-maven-3.9.1
export PATH=$PATH:$M2_HOME/bin

source ~/.bashrc
```

### Check version again now
```
mvn --version
mvn --help
```

## `*************************   EOF   *************************`
