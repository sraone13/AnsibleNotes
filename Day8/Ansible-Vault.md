In Ansible we can keep senstive data like our passwords and keys in encrypted format.



openssl rand -base64 2048 > vault.pass

ansible-vault aws_cred.yml

ansible-vault create aws_cred.yml --vault-password-file vault.pass

ansible-vault encrpt aws_cred.yml --vault-password-file vault.pass
 
ansible-vault view aws_cred.yml --vault-password-file vault.pass

ansible-vault edit aws_cred.yml --vault-password-file vault.pass

ansible-vault rekey aws_cred.yml --vault-password-file vault.pass

ansible-vault decreypt aws_cred.yml --vault-password-file vault.pass
 

ansible-vault decrypt aws_cred.yml
