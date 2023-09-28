# telerec-t-base
Basic Ansible Setup for a server with Traefik, Portainer and Watchtower.

## Install ansible

First [install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html). 
We recommend using `pipenv` with the Pipfile in the repository:
```shell
cd telerec-t-base
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
```

## Run the playbook

```shell script
pipenv run ansible-playbook server-setup.yml -i hosts
```

