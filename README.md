# Ansible Role: MySQL

Installs MySQL server on RedHat Enterprise Linux or CentOS 6.x servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `vars/main.yml`):

    mysql_enablerepo: ""

If you have enabled any additional repositories (might I suggest geerlingguy.repo-epel or geerlingguy.repo-remi), those repositories can be listed under this variable (e.g. `remi,epel`). This can be handy, as an example, if you want to install later versions of MySQL.

    mysql_root_password: root

The MySQL root user account password.

    mysql_packages:
      - mysql
      - mysql-server
      - MySQL-python

Packages to be installed. In some situations, you may need to add additional packages, like `mysql-devel`.

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

This role was created in 2014 by Jeff Geerling (@geerlingguy), author of Ansible for DevOps. You can find out more about the book at http://ansiblefordevops.com/, and learn about the author at http://jeffgeerling.com/.
