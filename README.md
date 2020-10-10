# Ansible Role: hosts

[![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](licence) [![Ansible Role](https://img.shields.io/ansible/role/24841?label=role%20name&style=flat-square)](https://galaxy.ansible.com/arillso/hosts) [![Ansible Role](https://img.shields.io/ansible/role/d/24841.svg?style=flat-square)](https://galaxy.ansible.com/arillso/hosts) [![Ansible Quality Score](https://img.shields.io/ansible/quality/24841?label=role%20quality&style=flat-square)](https://galaxy.ansible.com/arillso/hosts) [![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/arillso/ansible.hosts?style=flat-square)](https://github.com/arillso/ansible.hosts/releases) [![GitHub Workflow Status (branch)](https://img.shields.io/github/workflow/status/arillso/ansible.hosts/Role%20Tests/master?label=integration%20tests&style=flat-square)](https://github.com/arillso/ansible.hosts/actions?query=workflow%3A%22Role+Tests%22) [![GitHub last commit (branch)](https://img.shields.io/github/last-commit/arillso/ansible.hosts/master?style=flat-square)](https://github.com/arillso/ansible.hosts/commits/main)

## Description

Ansible role that dynamically creates the hosts file.

## Installation

```bash
ansible-galaxy install arillso.hosts
```

## Requirements

None

## Role Variables

### hosts_file

Path to the host file on the target system.

```yml
hosts_file: /etc/hosts
```

### hosts_backup

Backup the hosts file before changing it.

```yml
hosts_backup: false
```

### hosts_group

Group owner of hosts file.

```yml
hosts_group: root
```

### hosts_owner

Owner of hosts file.

```yml
hosts_owner: root
```

### hosts_mode

Access permission hosts file.

```yml
hosts_mode: 0644
```

### SELinux

Settings for SElinux.

```yml
hosts_serole: object_r
hosts_setype: net_conf_t
hosts_seuser: system_u
hosts_selevel: s0
```

### Loopback

Creates a 127.0.0.1 entry for the server name.

```yml
hosts_hostname_loopback: true
```

### Inventory

Inserts all hosts in the Ansible Inventory file into the Hosts file.

```yml
hosts_inventory_to_hosts: false
```

For `hosts_inventory_to_hosts` to work, the variable `internel_ansible_host` must be set in the `host_vars`, alternative can also be set to `ansible_host`.
Optionally, `hosts_aliases` can be set in the `host_vars`, then it generates aliases for the hosts.

### IPv6

Ipv6 localhost entries are set automatically. Setting false it can be prevented.

```yml
hosts_ipv6: true
```

### IPv4 address

Address that you would like to use as IPv4 address. This could be overriden by what you want.

```yml
hosts_ipv4_address: "{{ hostvars[inventory_hostname]['ansible_default_ipv4']['address'] }}"
```

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
    - arillso.hosts
```

## Author

- [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2020, Arillso
