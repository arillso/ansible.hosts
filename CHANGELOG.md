# Changelog

This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
and [human-readable changelog](https://keepachangelog.com/en/1.0.0/).

## 1.7.3

### Fixed

- Fix newline issue for hosts_dns_hostname
- Correcting the readme

## 1.7.2

### Fixed

- Fix error message when hosts_aliases is not defined

### Changed

- Replace groups['all'] by hosts_inventory_to_hosts to use only the targeted group in playbook (can be all also)
- Rewrite template to not add duplicates
- Improve the IPv6 part

## 1.7.1

### Fixed

- fix SELinux error.

## 1.7.0

### Added

- add option for `hosts_backup`, `hosts_group`, `hosts_owner` and `hosts_mode`
- add option SELinux

## 1.6.0

### Changed

- update min ansible version to 2.8
- changelog to your own file
- travis file has been updated
- Documentation has been improved

### Added

- molecule testing

### 1.5.0

### Added

- Add option for ipv6 enable or disable

### Changed

- Change check from `ansible_default_ipv6.address` to `ansible_lo.ipv6`

### 1.4.0

### Added

- Add newline at end of each hostname entry of hosts_dns_hostname

### Changed

- Fix ipv6 entries

### 1.3.0

### Added

- add support for dns lists

### 1.2.0

### Changed

- sort templates ipv4 and ipv6 address

### 1.1.0

### Added

- option internel_ansible_host

### Changed

- hosts_inventory_to_hosts to internel_ansible_host by hosts_aliases

## 1.0.0

### Added

- inital Release
