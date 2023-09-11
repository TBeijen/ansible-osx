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

## TODO:

* Configure git using ansible 

```sh
git config --global commit.gpgsign true
git config --global user.signingkey 058FED1DA5DDA152
```

Adding to `~/.gitconfig`:

```ini
[include]
	path = ~/dotfiles/common/.gitconfig

[includeIf "gitdir:~/projects/<client>/"]
	path = ~/.gitconfig-<client>
```

Example `~/.gitconfig-<client>`:

```ini
[user]
	name = Tibo Beijen
	email = tibo.beijen@<client-domain
	signingkey = 123FOOBAR
```

Figure out why appstore tailscale works and brew tailscale 'hangs'

## References:

* https://github.com/mrlesmithjr/developers-workstation-setup/tree/master
* https://github.com/hnakamur/ansible-role-osx-defaults/blob/master/library/osx_defaults

PGP

* https://gist.github.com/troyfontaine/18c9146295168ee9ca2b30c00bd1b41e

Minikube

* https://devopscube.com/minikube-mac/#:~:text=This%20blog%20contains%20the%20guide,based%20systems%20without%20any%20issues.