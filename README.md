# guacamole-docker

Ansible role for installing and running dockerized Wordpress stack.

Deploys 2 containers:
* mariadb
* guacamole

## Getting Started

### Prerequisites

* Ansible
* Docker

Docker can be deployed from one of many galaxy roles, such as [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker).

### Installing

```
$ ansible-galaxy install robrowan.wordpress_docker
```

## Use

### Role Variables

Defaults

```
mysql_database: wp-db
mysql_user: user
mysql_password: password
mysql_root_password: password
```
Overwrite these defaults (recommended) using a hosts var file, or just extra vars.

### Example playbook

```
- hosts: wordpress_servers
  roles:
    - robrowan.wordpress_docker
  become: true
```

Include a docker role:
```
- hosts: wordpress_servers
  roles:
    - robrowan.docker
    - robrowan.guacamole_docker
  become: true
```

## Authors

* **Rob Rowan** - [RobRowan](https://github.com/robrowan)

## License

This project is licensed under the MIT License.
