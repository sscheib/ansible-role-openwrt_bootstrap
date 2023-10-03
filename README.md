openwrt_bootstrap
=========

Bootstrap Ansible on OpenWrt.

Requirements
------------

A device that has enough flash storage space available to hold either a full-blown python3 installation or the minimal set of python dependencies:
- 'python3-light'
- 'python3-base'
- 'libffi'
- 'python3-logging'
- 'python3-multiprocessing'
- 'python3-distutils'
- 'python3-email'

Role Variables
--------------
```
**Optional**
- minimal_required_packages: minimal required packages for Ansible to work
  Default value:
    - 'python3-light'
    - 'python3-base'
    - 'libffi'
    - 'python3-logging'
    - 'python3-multiprocessing'
    - 'python3-distutils'
    - 'python3-email'

- full_required_packages: Python3 full installation packages
  Default value:
    - 'python3'

- install_full_python: whether to install the full Python3 version
  Default value: false

- update_opkg_cache: whether to update opkg cache before attempting to install the packages (recommended)
  Default value: true
```

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
