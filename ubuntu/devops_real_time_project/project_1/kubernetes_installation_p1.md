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
Pending        
```


## `*************************   EOF   *************************`