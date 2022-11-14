# JENKINS INSTALLATION ON UBUNTU


#### `**** Please Like & Subscribe My Channel To Motivate Me ****`


#### Install Java  Prerequisite
```
$ sudo su
$ sudo apt update
$ hostname
$ hostnamectl set-hostname jenkins
$ bash
$ java -version
$ apt-get install openjdk-11-jdk -y
$ java -version
```

<br />


#### Install Jenkins 
```
$ wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
$ echo deb https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
$ sudo apt-get update
$ sudo apt-cache madison jenkins    
$ sudo apt-get install jenkins -y                         ## jenkins=2.361.3
$ sudo systemctl start jenkins
$ sudo systemctl enable jenkins
$ sudo systemctl status jenkins
```


<br />


#### Access Jenkins via Browser
```
http://[public_server_ip]:8080 
```

<br />


#### Update firewall rules in SG 
```
Open Port : 8080
```

<br />


#### Check about jenkins version details
```
http://[public_server_ip]/about/
```


<br />


#### Get Jenkins Administrator password using this command
```
$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

<br />

#### `**** Please Like & Subscribe My Channel To Motivate Me ****`
  

We'll provide DevOps real time project in upcoming video in this channel. So please subscribe my channel.

## `*************************   EOF   *************************`

