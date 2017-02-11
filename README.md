[![Build Status](https://travis-ci.org/zaxos/guacamole-ansible-role.svg?branch=master)](https://travis-ci.org/zaxos/guacamole-ansible-role)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-_zaxos.guacamole--ansible--role-blue.svg)](https://galaxy.ansible.com/zaxos/guacamole-ansible-role/)

guacamole-ansible-role
======================

Ansible role to install and configure Guacamole with MySQL/MariaDB.

Requirements
------------
* centos/rhel 7
* ansible >=2.2
* selinux disabled

Installation
------------
```
$ ansible-galaxy install zaxos.guacamole-ansible-role
```

Example Playbook
----------------
```yaml
    - hosts: servers
      vars:
        guacamole_mysql_root_password: MY-PASSWORD-HERE
      roles:
        - role: zaxos.guacamole-ansible-role
```

Role Variables
--------------
Some variables that require review:
- `guacamole_mysql_root_password`: Password for root user to be created for local mariadb installation.
- `guacamole_db_name`: Database name used by guacamole. Default is "guac_db".
- `guacamole_db_username`: Database user used by guacamole. Default is "guac_db_usr".
- `guacamole_db_password`: Database user password used by guacamole. Default is "guacdbpassword".

Some defaults (probably not requiring tampering):
- `guacamole_temp_path`: /tmp/guactempdir   
Temporary directory used for deployment. It will be deleted afterwards.

Usage
-----
After installation, point your browser to: `http://IP_or_FQDN:8080/guacamole`   
Default username and password is: `guacadmin`   
*(Don't forget to change it)*
