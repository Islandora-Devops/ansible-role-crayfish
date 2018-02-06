# Ansible Role: Crayfish [![Build Status](https://travis-ci.org/Islandora-Devops/ansible-role-crayfish.svg?branch=master)](https://travis-ci.org/Islandora-Devops/ansible-role-crayfish)

An Ansible role that installs [Crayfish](https://github.com/Islandora-CLAW/Crayfish) on:

* Centos/RHEL 7.x
* Ubuntu Xenial

## Role Variables

Available variables are listed below, along with default values:

```
# User to install crayfish with (usually the webserver user)
crayfish_user: www-data
crayfish_group: www-data
# Crayfish version to install
crayfish_version_tag: 0.0.7
# Crayfish services to install
crayfish_services:
  - Gemini
  - Houdini
  - Milliner
  - Hypercube
# Default crayfish static JWT token
crayfish_syn_token: islandora
# Webserver path to install to
crayfish_install_dir: /var/www/html/Crayfish
# Crayfish log directory
crayfish_log_dir: /var/log/islandora
# Apache configuration directory
crayfish_apache_conf_dir: /etc/apache2
```

`crayfish_db` can be set to: 
 - pgsql 
 - mysql

 Depending what database you would like to use.

There are lots more configuration settings in [defaults/main.yml](defaults/main.yml)

## Dependencies

The module depends on the following. Links are provided to roles known to work with the mdoule, but should be able to work with any role providing the required software:
* [Apache](https://galaxy.ansible.com/geerlingguy/apache/)
* [PHP](https://galaxy.ansible.com/geerlingguy/php/)
* [Composer](https://galaxy.ansible.com/geerlingguy/composer/)
* [git](https://galaxy.ansible.com/geerlingguy/git/)
* database
  - [pgsql](https://galaxy.ansible.com/geerlingguy/postgresql/)
  - [mysql](https://galaxy.ansible.com/geerlingguy/mysql/)
  
## Example Playbook

Examples from the role tests: 
* [Postgresql](tests/pgsql.yml)
* [Mysql](tests/mysql.yml)

## License

MIT
