Roles:
Galaxy: https://galaxy.ansible.com/ui/standalone/roles/

ansible-galaxy role init <role_name>


1. How to add the roles from the galaxy
ansible-galaxy role install bsmeding.docker

~/.ansible/roles/

run the ansible-playbook


2. How to push the roles from the galaxy

Go the role
cd rolename
 
git init
git remote add origin https://github.com/sraone13/Ansible-role.git
git add .
git commit -u "commit message"
git push -u origin master or main

if any error comes, add the pubkey which in /etc/ssh/rsa.pub/
copy that and add in GitHub add ssh keys.

still if it ask the passwords while pushing to GitHub, run below commads

git remote set-url origin git@github.com:sraone13/Ansible-role.git
git config --global credential.helper cache
git config --global credential.helper 'cache --timeout=3600'


git push -u origin master or main

ansible-galaxy import sraone13 Ansible-role --token 365e2585968e1de5fd3e950dec435cf6b95eb6da




