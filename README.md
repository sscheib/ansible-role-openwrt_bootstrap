<!-- markdownlint-disable MD013 MD041 -->
[![ansible-lint](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/ansible-lint.yml) [![Publish to Ansible Galaxy](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/release.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/release.yml) [![markdown link check](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/markdown-link-check.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/markdown-link-check.yml) [![markdownlint](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/markdownlint.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/markdownlint.yml) [![pyspelling](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/pyspelling.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/pyspelling.yml) [![commitlint](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/commitlint.yml/badge.svg)](https://github.com/sscheib/ansible-role-openwrt_bootstrap/actions/workflows/commitlint.yml)

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit) [![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-%23FE5196?logo=conventionalcommits)](https://conventionalcommits.org) [![License: GPL v2](https://img.shields.io/badge/License-GPL_v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
<!-- markdownlint-disable MD013 MD041 -->

## openwrt_bootstrap

Bootstrap Python on `OpenWrt` devices by installing the required Python packages for Ansible to run.

**Please note**:

- Since Python is probably not installed on the `OpenWrt` device at this point, please make sure to disable gathering of facts in the playbook (`gather_facts: false` - see
  the [example playbook](#example-playbook))

## Requirements

A device that has enough flash storage space available to hold either a full-blown `python3` installation or the minimal set of Python dependencies:

- `python3-light`
- `python3-base`
- `libffi`
- `python3-logging`
- `python3-multiprocessing`
- `python3-distutils`
- `python3-email`
- `python3-urllib`

## Role Variables

| variable                          | default                      | required | description                                                                    |
| :---------------------------------| :--------------------------- | :------- | :----------------------------------------------------------------------------- |
| `bts_minimal_required_package`    | See `defaults/main.yml`      | false    | Minimal required packages for Ansible to work                                  |
| `bts_full_required_packages`      | `['python3']`                | false    | Python3 full installation packages                                             |
| `bts_install_full_python`         | `false`                      | false    | Whether to install the full Python3 version                                    |
| `bts_update_opkg_cache`           | `true`                       | false    | Whether to update `opkg` cache before attempting to install the packages       |

## Dependencies

None

## Example Playbook

```yaml
---
- hosts: 'all'
  gather_facts: false
  vars:
    install_full_python: true
  roles:
    - 'openwrt_bootstrap'
...
```

## Contributing

First off, thanks for taking the time to contribute! ❤️

All types of contributions are encouraged and valued.
Please see the [`CONTRIBUTING.md`](CONTRIBUTING.md) for different ways to help and details about how this project handles them.

## License

[`GPL-2.0-or-later`](LICENSE)
