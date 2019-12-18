Centos7, Symfony4 Website
==========================

Install a Symfony4 website from a git repo on Centos7.

Requirements
------------

Apache with SSL, PHP >= 7, git and MySQL / MariaDB.

Role Variables
--------------

### Has default value

- install_repo_version
- ssl_cert_file
- ssl_cert_key_file
- env_extra
- env_app_env
- env_app_debug
- env_php_version
- env_domain_name
- env_database_port
- env_database_host

### Has no default value

- env_database_name
- env_database_user
- env_database_password
- env_database_root_password
- env_app_secret
- install_dir_name
- install_repo_ssh


Dependencies
------------

- geerlingguy.composer

Example Playbook
----------------

```
---
- name: Install a Symfony4 website from a git repo on Centos7
  hosts: all
  become: true
  vars:
    env_database_name: fizizzle_dev
    env_database_root_password: foo
    env_database_user: bar
    env_database_password: baz
    env_app_secret: superSecretKeyTellNoone
    install_dir_name: fizizzle
    install_repo_ssh: git@git.example.com:username/repo.git
  tasks:
  - include_role: 
      name: myrostadler.centos7_symfony4_website
```

License
-------

GPL-3.0-only

Author Information
------------------

Myro Stadler