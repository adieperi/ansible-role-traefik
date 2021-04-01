# ansible-role-traefik
Ansible Role to install the traefik binary

## How to install
### requirements.yml
**Put the file in your roles directory**
```yaml
---
- src: https://github.com/adieperi/ansible-role-traefik.git
  scm: git
  version: master
  name: ansible-role-traefik
```
### Download the role
```Shell
ansible-galaxy install -f -r ./roles/requirements.yml --roles-path=./roles
```
## Exemple Playbook
```yaml
---
- hosts: all
  tasks:
    - name: Include ansible-role-traefik
      include_role:
        name: ansible-role-traefik
      vars:
        traefikVersion: 2.4.8
```
