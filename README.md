# Ansible NodeJS

An Ansible role that installs NodeJS on Ubuntu based on the official installation instructions.

##  Requirements

N/A

## Role Variables

`nodejs_version`: version of node to install

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

BSD

## Author Information

https://calvin.me
