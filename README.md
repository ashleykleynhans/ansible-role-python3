# ansible-role-python3

Ansible role to upgrade Python3 to the latest version (currently 3.10) on Ubuntu 18.04 LTS and Ubuntu 22.04 LTS.

Ubuntu 22.04 LTS is packaged with Python 3.10 by default so no upgrade is required.

This role upgrades Python3 and also **resolves the following issues** after upgrade:

* Issues with apt_pkg and apt_inst.
* System becoming inaccessible by Ansible.
* System becoming inaccessible after reboot.
* System becoming inaccessible by cloud-init to launch a new EC2 instance from an AMI.

## Requirements

None.

## Role Variables

| Variable               | Value  |
|------------------------|--------|
| python_version_upgrade | "3.10" |

**Note:** The version needs to be in quotes, otherwise Ansible treats it as a float, and 3.10 becomes 3.1 which results in errors.

## Dependencies

None.

## Example Playbook

```yml
---
- name: Upgrade python3
  hosts: all
  gather_facts: no

  tasks:
    - name: Include role ansible-role-python3
      include_role:
        name: ansible-role-python3
```

## License

GPLv3

## Author Information

Ashley Kleynhans
