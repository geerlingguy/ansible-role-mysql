# Ansible Role: MySQL
This is a fork of the [geerlingguy.mysql](https://github.com/geerlingguy/ansible-role-mysql) role which adds the ability to specify the MySQL version to install on Debian/Ubuntu platforms.

See [geerlingguy.mysql](https://github.com/geerlingguy/ansible-role-mysql#ansible-role-mysql) for instruction on how to use this role.

## Requirements
None.

## Role Variables
Available variables are listed below, along with their default values.
See [geerlingguy.mysql role variables](https://github.com/geerlingguy/ansible-role-mysql#role-variables) for information on the core variables that this role uses.

```yaml
mysql_version: "5.7"
```
Security settings for SSH.
- `mysql_version:string` - Specifies whether ssh-agent forwarding is permitted.

## Dependencies
None.

## Example Playbook
```yaml
- hosts: server
  become: yes

  vars:
    mysql_version: "8.0"
    mysql_root_password: super-secure-password
    mysql_databases:
      - name: example_db
        encoding: latin1
        collation: latin1_general_ci
    mysql_users:
      - name: example_user
        host: "%"
        password: similarly-secure-password
        priv: "example_db.*:ALL"

  tasks:
  - import_role:
      name: damianlewis.mysql
```

## License
MIT

## Author
Damian Lewis
