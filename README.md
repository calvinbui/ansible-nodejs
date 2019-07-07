[![Build Status](https://travis-ci.com/calvinbui/ansible-nodejs.svg?branch=master)](https://travis-ci.com/calvinbui/ansible-nodejs)
![Ansible Quality Score](https://img.shields.io/ansible/quality/35860.svg)
![Ansible Role](https://img.shields.io/ansible/role/d/35860.svg)

# Ansible NodeJS

An Ansible role that installs NodeJS & NPM on Ubuntu based on the official installation instructions.

##  Requirements

N/A

## Role Variables

`nodejs_version`: version of node to install

`nodejs_install_packages`: A list of packages to install with the npm module. Set it to `[]` if no packages are required.

[All available options used in the npm module can be used here as well](https://docs.ansible.com/ansible/2.7/modules/npm_module.html). Set it exactly the same as the pip module, e.g.

```
nodejs_install_packages:
  - name: lodash
    global: true
  - name: request
    state: present
    version: 2.88.0
    global: true
    production: true
    ignore_scripts: true
  - ...
```

## Dependencies

N/A

## Example Playbook

```yaml
- hosts: servers
  become: true
  pre_tasks:
    - name: Update apt cache.
      apt:
        update_cache: true
        cache_valid_time: 600
      changed_when: false
  roles:
     - role: ansible-nodejs
```

## License

GPLv3

## Author Information

https://calvin.me
