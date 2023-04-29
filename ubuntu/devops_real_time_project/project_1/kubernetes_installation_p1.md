## KUBERNETES CLUSTER INSTALLATION

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
hostnamectl set-hostname k8-master
bash
```

### Install Java
```
java -version
apt-get install openjdk-17-jdk -y       ## For sonarqube-10.0.0.68432.zip
apt-get install openjdk-11-jdk -y       ## For sonarqube-8.9.2.46101.zip
java -version         
```


## `*************************   EOF   *************************`