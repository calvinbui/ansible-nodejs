# Ansible NodeJS

An Ansible role that installs the latest version of NodeJS on Ubuntu based on the official installation instructions.

## Requirements

None

## Role Variables

`nodejs_version`: version of node to install

## Dependencies

None

## Example Playbook

```
- hosts: servers
  roles:
     - role: ansible-nodejs
```

## License

BSD

## Author Information

https://calvin.me
