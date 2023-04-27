## SONARQUBE INSTALLATION

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
hostnamectl set-hostname sonarqube
bash
```

### Install Java
```
java -version
apt-get install openjdk-17-jdk -y       ## For sonarqube-10.0.0.68432.zip
apt-get install openjdk-11-jdk -y       ## For sonarqube-8.9.2.46101.zip
java -version         
```

### Install Sonarqube
```
cd /opt/
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.0.0.68432.zip
OR
wget wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-8.9.2.46101.zip
unzip sonarqube-10.0.0.68432.zip
mv sonarqube-10.0.0.68432 sonarqube
```

### Create sonar user
```
useradd -d /opt/sonarqube sonar
cat /etc/passwd | grep sonar
chown -R sonar:sonar /opt/sonarqube
ls -l /opt/sonarqube
```

### Create custom service for sonar
```
cat >> /etc/systemd/system/sonarqube.service <<EOL
[Unit]
Description=SonarQube service
After=syslog.target network.target

[Service]
Type=forking
User=sonar
Group=sonar
PermissionsStartOnly=true
ExecStart=/opt/sonarqube/bin/linux-x86-64/sonar.sh start 
ExecStop=/opt/sonarqube/bin/linux-x86-64/sonar.sh stop
StandardOutput=syslog
LimitNOFILE=65536
LimitNPROC=4096
TimeoutStartSec=5
Restart=always

[Install]
WantedBy=multi-user.target
EOL


ls -l /etc/systemd/system/sonarqube.service
```

### Open port 9000 from firewalld OR security group.
```
9000
```

### Service start & enable
```
systemctl start sonarqube.service
systemctl enable sonarqube.service
systemctl status sonarqube.service
```

### check 9000 port is used or not
```
netstat -plant | grep 9000
```

### Open sonarqube on browser
```
URL:   http://192.168.1.70:9000/projects/create

U: admin
P: admin

New Pass: admin@123
```
