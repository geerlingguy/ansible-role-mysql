# Ansible Role: MySQL

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-mysql.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-mysql)

Installs MySQL server on RHEL/CentOS or Debian/Ubuntu servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `vars/main.yml`):

    mysql_user_home: /root

The home directory inside which Python MySQL settings will be stored, which Ansible will use when connecting to MySQL. This should be the home directory of the user which runs this Ansible role.

    mysql_root_password: root

The MySQL root user account password.

    mysql_packages:
      - mysql
      - mysql-server
      - MySQL-python

(OS-specific, RedHat/CentOS defaults listed here) Packages to be installed. In some situations, you may need to add additional packages, like `mysql-devel`.

    mysql_enablerepo: ""

(RedHat/CentOS only) If you have enabled any additional repositories (might I suggest geerlingguy.repo-epel or geerlingguy.repo-remi), those repositories can be listed under this variable (e.g. `remi,epel`). This can be handy, as an example, if you want to install later versions of MySQL.

## Dependencies

None.

## Example Playbook

    - hosts: db-servers
      vars_files:
        - vars/main.yml
      roles:
        - { role: geerlingguy.mysql }

*Inside `vars/main.yml`*:

    mysql_root_password: super-secure-password

## TODO

  - Convert my.cnf configuration to template, and allow for configurable variables.

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
