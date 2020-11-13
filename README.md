# Ansible Role: MySQL
This is a fork of the [damianlewis.mysql](https://github.com/damianlewis/ansible-role-mysql/) role which adds the ability to do things such as specify the MySQL version to install on Debian/Ubuntu platforms and disable binary logs.

See [damianlewis.mysql](https://github.com/damianlewis/ansible-role-mysql/) and [geerlingguy.mysql](https://github.com/geerlingguy/ansible-role-mysql#ansible-role-mysql) for instruction on how to use this role.

## Requirements
None.

## Role Variables
Available variables are listed below, along with their default values.
See [damianlewis.mysql](https://github.com/damianlewis/ansible-role-mysql/) and [geerlingguy.mysql role variables](https://github.com/geerlingguy/ansible-role-mysql#role-variables) for information on the core variables that this role uses.

```yaml
mysql_version: "8.0"
```
MySQL installation settings.
- `mysql_version:string` - Specifies which version of MySQL to install.

## Dependencies
None.

## Example Playbook
```yaml
- hosts: server
  become: yes

  vars:
    mysql_version: "8.0"
    mysql_skip_name_resolve: true
    mysql_skip_log_bin: true
    mysql_root_password: super-secure-password
    mysql_databases:
      - name: example_db
        encoding: utf8
        collation: utf8_general_ci
    mysql_users:
      - name: example_user
        host: "%"
        password: similarly-secure-password
        priv: "example_db.*:ALL"

  tasks:
  - import_role:
      name: exoticca.mysql
```
