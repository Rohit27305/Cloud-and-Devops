# Ansible Realtime project
## Task
Create three(3) EC2 instances on AWS using Ansible loops
2 Instances with Ubuntu Distribution
1 Instance with Red-hat Distribution

Set up passwordless authentication between Ansible control node and newly created instances.

Automate the shutdown of Ubuntu Instances only using Ansible Conditionals

Hint: Use connection: local on Ansible Control node.

## Prerequisite
## 1. installed ```boto3```
## 2. ```ansible-galaxy collection install amazon.aws```
## 3. Vault Setup
use ```openssl rand -base64 2048 > vault.pass```

after that ```ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass```


# Solution
1. Go to task section in ansible-role and refer ```main.yml``` file
2. Add your pem file into Identity File using this commnad ```ssh-add <path_to_pem_file>``` to passwordless authentication
3. Run your playbook ```ansible-playbook <path_to_yml_file> --vault-password-file vault.pass``` to create your instances
4. Add all your servers in ```inventory.ini``` file
5. Run ```stop.yml``` file to shut down your ubuntu ec2 only 
6. Congratulation It's Done......