# +++++ TERRAFORM  INSTALLATION +++++

#### Update Ubuntu packages
```
$ sudo -i
$ apt-get update
```

<br />

#### Change hostname
```
$ hostnamectl set-hostname terraform
$ bash
$ hostname
```

<br />


#### Check Terraform version exist or not ?
```
$ terraform -v
```

<br />

#### Install Terraform
```
$ wget https://releases.hashicorp.com/terraform/1.3.4/terraform_1.3.4_linux_amd64.zip
$ apt-get install unzip
$ unzip terraform_1.3.4_linux_amd64.zip
$ ls -l
$ cp terraform /usr/bin/
```

<br />

#### Now check Terraform version
```
$ terraform -v
```

## `*************************   EOF   *************************`
