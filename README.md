[![Build Status](https://travis-ci.org/while-true-do/ansible-role-cronie.svg?branch=master)](https://travis-ci.org/while-true-do/ansible-role-cronie)

# Ansible Role: Cronie
| A role to install and configure Cronie / Crontabs.

## Motivation

Cronie contains the standard UNIX daemon crond that runs specified programs at scheduled times and related tools. This role will help with the setup and optional hardening of Cron.

## Installation

Install from [Ansible Galaxy](https://galaxy.ansible.com/while-true-do/cronie)

```
ansible-galaxy install while-true-do.cronie
```

Install from [Github](https://github.com/while-true-do/ansible-role-cronie)

```
git clone https://github.com/while-true-do/ansible-role-cronie.git while-true-do.cronie
```

## Requirements

Used Modules:

-   [file_module](http://docs.ansible.com/ansible/latest/file_module.html)
-   [template_module](http://docs.ansible.com/ansible/latest/template_module.html)
-   [package_module](http://docs.ansible.com/ansible/latest/package_module.html)
-   [service_module](http://docs.ansible.com/ansible/latest/service_module.html)
-   [include_tasks_module](https://docs.ansible.com/ansible/2.4/include_tasks_module.html)

## Dependencies

None.

## Role Variables

```yaml
---
# defaults/main.yml for cronie
# You can set the state to ["present"|"absent"|"latest"]
wtd_cronie_state: "present"
wtd_cronie_packages: ["cronie"]

# Hardening related Variables
# All user listed in cron.allows will be allowd to use cron
# cron.denys will be ignored, if cron.allows is used
# cron.allow will always "beat" cron.deny
wtd_cronie_allows: ["root"]
# All users listed in cron.denys will be forbidden to use cron
wtd_cronie_denys: []
```

## Example Playbook

Simple Example:

```yaml
- hosts: servers 
  roles:
    - { role: while-true-do.cronie }
```

## Testing

All tests are located in [test directory](./tests/).

Basic testing:

```
bash ./tests/test-spelling.sh
bash ./tests/test-ansible.sh
```

## Contribute / Bugs

Thank you so much for considering to contribute. Every contribution helps us.
We are really happy, when somebody is joining the hard work. Please have a look 
at the links first.

-   [Contribution Guidelines](./docs/CONTRIBUTING.md)
-   [Create an issue or Request](https://github.com/while-true-do/ansible-role-cronie/issues)
-   [See who was contributing already](https://github.com/while-true-do/ansible-role-cronie/graphs/contributors)

## License

This work is licensed under a [BSD License](https://opensource.org/licenses/BSD-3-Clause).

## Author Information

Blog: [blog.while-true-do.org](https://blog.while-true-do.org)

Mail: [hello@while-true-do.org](mailto:hello@while-true-do.org)
