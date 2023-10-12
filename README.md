# telerec-t-base
Basic Ansible Setup for a server with Traefik, Portainer, Autoheal and Watchtower.

Clone this repository with submodules:
```shell
git clone --recurse-submodules https://github.com/ct-Open-Source/telerec-t-base.git
```

## Install ansible

First install `sshpass` for the first login without public key. On Ubuntu or Debian use:
```shell
sudo apt install sshpass
```

Then [install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html). 
We recommend using `pipenv` with the Pipfile in the repository:
```shell
cd Pluto
pipenv install
```

The following commands use `pipenv` to run the ansible commands from within the virtual environment. 
If you installed Ansible without a virtualenv remove the trailing `pipenv run ` from the following commands.

### Install ansible modules

Ansible can be extended in different ways. To keep it small by default there is a plug-in repository called 
"Ansible Galaxy". For this setup you need these two plug-ins (also called "modules"): 

```shell script
pipenv run ansible-galaxy collection install ansible.posix
pipenv run ansible-galaxy collection install community.general
pipenv run ansible-galaxy role install geerlingguy.docker
```

## Run the playbook

For the first server setup you need to allow login with `--ask-pass`:

```shell
pipenv run ansible-playbook initial-setup.yml -i hosts --ask-pass --ask-become-pass
```

```shell script
pipenv run ansible-playbook server-setup.yml -i hosts
```