# Ansible Role: hosts

[![Build Status](https://travis-ci.org/arillso/ansible.hosts.svg?branch=master)](https://travis-ci.org/arillso/ansible.hosts) [![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://sbaerlo.ch/licence) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-hosts-blue.svg)](https://galaxy.ansible.com/arillso/hosts)

## Description

Ansible role that dynamically creates the hosts file.

## Installation

```bash
ansible-galaxy install arillso.hosts
```

## Requirements

## Role Variables

| Variable             | Default     | Comments (type)                                   |
| :---                 | :---        | :---                                              |
| hosts_hostname_loopback | true | Creates a 172.0.0.1 entry for the server name. |
| hosts_inventory_to_hosts | false | Inserts all hosts in the Ansible Inventory file into the Hosts file. |

### Note `hosts_inventory_to_hosts`

For `hosts_inventory_to_hosts` to work, the variable `internel_ansible_host` must be set in the `host_vars`, alternative can also be set to `ansible_host`.
Optionally, `hosts_aliases` can be set in the `host_vars`, then it generates aliases for the hosts.

## Dependencies

## Example Playbook

```yml
- hosts: all
  roles:
     - arillso.hosts
```

## Changelog

### 1.1

* add option internel_ansible_host
* change hosts_inventory_to_hosts to internel_ansible_host by hosts_aliases

### 1.0

* inital commit

## Author

* [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2018, Simon Bärlocher