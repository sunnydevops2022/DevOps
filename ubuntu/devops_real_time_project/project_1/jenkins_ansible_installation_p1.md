## ++++++++++++++++++ JENKINS INSTALLATION ++++++++++++++++++

#### Update repository of ubuntu
```
sudo -i
sudo apt-get update
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
sudo apt-get install jenkins=2.361.3
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
sudo apt-get install ansible
```

### Now check Ansible version
```
ansible --version
```

<br/>
<br/>

## `*************************   EOF   *************************`