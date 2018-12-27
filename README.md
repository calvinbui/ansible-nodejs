# Ansible NodeJS

An Ansible role that installs NodeJS & NPM on Ubuntu based on the official installation instructions.

##  Requirements

N/A

## Role Variables

`nodejs_version`: version of node to install

`nodejs_install_packages`: A list of packages to install with the npm module. Set it to `[]` if no packages are required.

[All available options used in the npm module can be used here as well](https://docs.ansible.com/ansible/2.7/modules/npm_module.html). Available options:

```
name
version
state
executable
global
ignore_scripts
path
production
registry
```

Notes:
- `global` is omitted if `path` is defined. `global` is 'true' otherwise.

Examples:

```yaml
npm_install_packages:
  # by itself installs with 'global'
  - lodash

  # with path will define where to install
  - name: express
    path: /home/calvin/my-node-app/

  # with some options
  - name: requests
    state: present
    version: 2.88.0
    ignore_scripts: true

  # within a project
  - name: chalk
    path: /home/calvin/my-node-app/

  # within a project, install the package.json
  - path: /home/calvin/my-node-app/
    production: true

  # with a different executable than bin path (i.e. nvm)
  - path: /home/calvin/my-node-app/
    executable: /opt/nvm/v0.10.1/bin/npm
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
