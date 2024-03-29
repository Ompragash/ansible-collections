## Requirements

- ansible
- python3-psycopg2
- python3-firewall
- httpie
- jq

## Clone ansible-pulp GitHub repository

```
# git clone https://github.com/pulp/ansible-pulp.git

# cd ansible-pulp/
```

## Create pulp_ansible.yml with the below contents

```
---
- hosts: all
  vars:
    pulp_settings:
      secret_key: secret
      ansible_api_hostname: 'http://localhost:24817'
      ansible_ansible_content_hostname: 'http://localhost:24816/pulp/content'
    pulp_default_admin_password: password
    pulp_install_plugins:
      pulp-ansible:
        app_label: "ansible"
  roles:
    - pulp-database
    - pulp-workers
    - pulp-resource-manager
    - pulp-webserver
    - pulp-content
  environment:
    DJANGO_SETTINGS_MODULE: pulpcore.app.settings
```

## Run pulp_ansible.yml playbook to deploy pulp_ansible

```
    ansible-playbook pulp_ansible.yml
```

## Check pulp_ansible status

```
    http http://localhost/pulp/api/v3/status/
```
additionally you can also run ```systemctl --all | grep pulp``` to check for all pulp services.

## Configure ~/.netrc and it can be used by "http" utility for basic authentication

```
# vim ~/.netrc
machine localhost
login username
password password
```
