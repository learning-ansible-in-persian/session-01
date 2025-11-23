### Requirements:

1. **VirtualBox** 
https://www.virtualbox.org/wiki/Downloads

2. **Vagrant** 
https://developer.hashicorp.com/vagrant/install

3. **Ansible**

### Commands
```bash
# get codes
git clone https://github.com/learning-ansible-in-persian/session-01.git && cd session-01

# setup machines
vagrant up --provider virtualbox

# setup machine 10 using setup.sh script
ssh vagrant@192.168.56.110 -i .vagrant/machines/ansible10/virtualbox/private_key 'bash -s' < setup.sh

# setup ansible
python -m venv ansible_venv
source ansible_venv/bin/activate
pip install ansible

# setup machine 1..9 using setup.yml playbook
ansible all -m ping -i hosts.ini
ansible-playbook -i hosts.ini setup.yml
```
