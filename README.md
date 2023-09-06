# Ansible OS-X home setup

## Prerequisites

* Set up ssh private key for git pull
* Install ansible

```
# SSH setup
#
mkdir ~/.ssh
chmod 0700 ~/.ssh
# (illustrative purposes, download key and check permissions)
touch ~/.ssh/id_ed25519
chmod 0600 ~/.ssh/id_ed25519 

# Ansible
# See: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installation-guide
#
python3 -m pip install --user ansible

# Update path
export PATH="$HOME/Library/Python/3.9/bin:$PATH"
```

## Usage

```
git clone git@github.com:TBeijen/ansible-osx.git
cd ansible-osx
ansible-playbook osx.yaml
```

 
## References:

* https://github.com/mrlesmithjr/developers-workstation-setup/tree/master
* https://github.com/hnakamur/ansible-role-osx-defaults/blob/master/library/osx_defaults
