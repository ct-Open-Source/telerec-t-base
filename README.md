# telerec-t-base
Basic Ansible Setup for a server with Traefik, Portainer and Watchtower

Run the playbook:

```shell script
ansible-playbook server-setup.yml -i hosts
```

## Install ansible modules

```shell script
ansible-galaxy collection install ansible.posix
ansible-galaxy collection install community.general
```