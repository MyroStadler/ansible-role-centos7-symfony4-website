Centos7, Symfony4 Website
==========================

Install a Symfony4 website from a git repo on Centos7.

Requirements
------------

Apache with SSL, PHP >= 7, git and MySQL / MariaDB.

Role Variables
--------------

### Has default value

Please see `defaults/main.yml` for defaults.

### Has no default value

- website_install_env_database_name
- website_install_env_database_user
- website_install_env_database_password
- website_install_env_database_root_password
- website_install_env_app_secret
- website_install_dir_name
- website_install_repo_ssh_uri


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
    website_install_env_database_name: fizizzle_dev
    website_install_env_database_root_password: foo
    website_install_env_database_user: bar
    website_install_env_database_password: baz
    website_install_env_app_secret: superSecretKeyTellNoone
    website_install_dir_name: fizizzle
    website_install_repo_ssh_uri: git@git.example.com:username/repo.git
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