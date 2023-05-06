# +++++ PROJECT-1 +++++

### Last Tested
```
Date:  05-May-2023
```

### Pre-Requisites
1. Install Jenkins
1. Install Ansible
1. Install Apache Maven
1. Install Sonarqube
1. Install Kubernetes Cluster
1. Git Account
1. Dockerhub Account

<br/>
<br/>

## +++++++++++++++++++++++++++ DAY 1 ++++++++++++++++++++++++++++

### Setup EC2 servers along with Github account.

<br/>

1. **[Install Jenkins & Ansible & Maven ](https://github.com/sunnydevops2022/DevOps/blob/master/ubuntu/devops_real_time_project/project_1/jenkins_ansible_installation_p1.md)**

1. **[Install Sonarqube](https://github.com/sunnydevops2022/DevOps/blob/master/ubuntu/devops_real_time_project/project_1/sonarqube_installation_p1.md)**

1. **[Install Kubernetes Cluster](https://github.com/sunnydevops2022/DevOps/blob/master/ubuntu/devops_real_time_project/project_1/kubernetes_installation_p1.md)**

1. **[Git Account](https://github.com/)**

1. **[Dockerhub Account](https://hub.docker.com/)**


<br/>
<br/>
<br/>
<br/>

## +++++++++++++++++++++++++++ DAY 2 ++++++++++++++++++++++++++++

## Jenkins integration with Sonarqube server.

### Go to Jenkins and install SonarQube Scanner plugin.
```
Dashboard > Manage Jenkins > Credentials > System Global credentials (unrestricted) > Add credentials > 
                                                                                            kind: Secret text
                                                                                            Scope: Global
                                                                                            Secret: token
                                                                                            ID: SONAR_TOKEN
                                                                                            Des: SONAR_TOKEN
Create
```

## Password less authentication with Kubernetes server.
```
vim /etc/ansible/hosts

[kubernetes]
<kubernetes_ip>


ansible -m ping all
ssh root@<kubernetes_ip>
ssh-keygen
ssh-copy-id root@<kubernetes_ip>
ssh root@<kubernetes_ip>
```

<br/>
<br/>
<br/>
<br/>

## +++++++++++++++++++++++++++ DAY 3 ++++++++++++++++++++++++++++



<br/>
<br/>
<br/>
<br/>

## `*************************   EOF   *************************`
