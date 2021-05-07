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

## Requirements

- Ansible >= 2.10 **(No tests has been realized before this version)**

## Role Variables

All variables which can be overridden are stored in [default/main.yml](default/main.yml) file as well as in table below.

| Name           | Default Value | Choices | Description                        |
| -------------- | ------------- | ------- | -----------------------------------|
| `traefik_version` | "2.4.8" | [version](https://github.com/traefik/traefik/tags) | Choice of the traefik version. |
| `traefik_acceslog_buffering_size` | "100" | An integer value | This option represents the number of log lines Traefik will keep in memory before writing them to the selected output. |
| `traefik_dashboard_enabled` | "true" | true / false | Disable the Traefik dashboard |
| `traefik_dashboard_pilot_enable` | "false" | true / false | Activate or not the "Connect with Traefik Pilot" button |
| `traefik_logs_level` | "ERROR" | DEBUG / PANIC / FATAL / ERROR / WARN / INFO | Choice of the log level |

## Example Playbook

```yaml
---
- hosts: all
  tasks:
    - name: Include ansible-role-traefik
      include_role:
        name: ansible-role-traefik
      vars:
        traefik_version: 2.4.8
```
## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.

## Maintainers and Contributors

- [Anthony Dieperink](https://github.com/adieperi)