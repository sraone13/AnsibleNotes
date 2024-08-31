# Install and Setup Ansible for Implementing Policy as Code on AWS

## Install boto3

```
pip install boto3
```

## Install AWS Collection

```
ansible-galaxy collection install amazon.aws
```

## Setup Vault 

1. Create a password for vault

```
openssl rand -base64 2048 > vault.pass
```

2. Add your AWS credentials using the below vault command

```
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass

```


## Conncetion with AWS:


1.Install curl unzip:

```
sudo apt install curl unzip

```



2.Download the latest version of the AWS CLI from Amazon's servers:

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

```

3.Unzip the downloaded files:

```
unzip awscliv2.zip

```
4.Install AWS CLI:

```
sudo ./aws/install
```

5.aws configure

access_key:
secret_key: