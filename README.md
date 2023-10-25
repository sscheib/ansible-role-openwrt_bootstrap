[![ansible-lint](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/ansible-lint.yml) [![Publish latest release to Ansible Galaxy](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/ansible-galaxy.yml/badge.svg?branch=main)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/ansible-galaxy.yml)

openwrt_bootstrap
=========

Bootstrap Ansible on OpenWrt.

Requirements
------------

A device that has enough flash storage space available to hold either a full-blown python3 installation or the minimal set of python dependencies:
- python3-light
- python3-base
- libffi
- python3-logging
- python3-multiprocessing
- python3-distutils
- python3-email

Role Variables
--------------
| variable                          | default                      | required | description                                                                    |
| :---------------------------------| :--------------------------- | :------- | :----------------------------------------------------------------------------- |
| `minimal_required_packages`       | See `defaults/main.yml`      | false    | minimal required packages for Ansible to work                                  |
| `full_required_packages`          | `['python3']`                | false    | Python3 full installation packages                                             | 
| `install_full_python`             | `false`                      | false    | whether to install the full Python3 version                                    |
| `update_opkg_cache`               | `true`                       | false    | whether to update opkg cache before attempting to install the packages         |

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: 'all'
  gather_facts: false
  vars:
    install_full_python: true
  roles:
    - 'openwrt_bootstrap'
```

License
-------

GPLv2 or later
