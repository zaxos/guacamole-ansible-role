[![Build Status](https://travis-ci.org/zaxos/guacamole-ansible-role.svg?branch=master)](https://travis-ci.org/zaxos/guacamole-ansible-role)

guacamole-ansible-role
==================

Ansible role to install and configure Guacamole with MySQL/MariaDB.

Requirements
------------
* centos/rhel 7  
* ansible >=2.2

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
        guacamole_db_name: guac_db
        guacamole_db_username: guac_db_usr
        guacamole_db_password: guacdbpassword
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
