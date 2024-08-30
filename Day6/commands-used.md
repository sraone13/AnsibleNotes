Collections:


1.Create the Collection in AWS with API(EC2 instance:

ansible-galaxy collection install amazon.aws
ansible-galaxy collection install amazon.aws --force

pip install boto3
apt install python3-pip
pip3 install boto3
sudo pip install boto3

ansible-galaxy role init ec2_create


ansible-playbook ansible-ec2.yaml

2.Create teh Vault:
openssl rand -base64 2048 > vault.pass
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass

3.Run Playbook with vaultpass:

ansible-playbook ansible-ec2.yaml --vault-password-file vault.pass

ansible-playbook ansible-ec2.yaml --vault-password-file vault.pass
