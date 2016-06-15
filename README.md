
William-Yeh.alpine-python for Ansible Galaxy
============

[![Build Status](https://travis-ci.org/William-Yeh/ansible-alpine-python.svg?branch=master)](https://travis-ci.org/William-Yeh/ansible-alpine-python) [![Circle CI](https://circleci.com/gh/William-Yeh/ansible-alpine-python.svg?style=shield)](https://circleci.com/gh/William-Yeh/ansible-alpine-python)


## Summary

Role name in Ansible Galaxy: **[William-Yeh.alpine-python](https://galaxy.ansible.com/William-Yeh/alpine-python/)**

This Ansible role has only one feature:

 - Install specific version of Python (2 and/or 3) under Alpine Linux.

Since Alpine Linux doesn't install Python by default, this role provides an easy way to enable Ansible to manage Alpine Linux machines.


## Role Variables

### Mandatory variables

None.



### Optional variables

User-configurable defaults:

```yaml
# install Python 2?
# default = yes
alpine_python_2_enabled: true

# install Python 3?
# default = no
alpine_python_3_enabled: false
```


Fix Alpine Linux repo list in `/etc/apk/repositories`?

```yaml
alpine_python_fix_repo: false 
```


## Usage


### Step 1: add role

Add role name `William-Yeh.alpine-python` to your playbook file.


### Step 2: add variables, if necessary

Set vars in your playbook file.

Simple example:

```yaml
---
# file: simple-playbook.yml

- hosts: all
  become: True
  gather_facts: false

  roles:
    - William-Yeh.alpine-python

  vars:
    alpine_python_3_enabled: true
```


## Dependencies

None.


## License

Licensed under the MIT License. See the [LICENSE file](LICENSE) for details.
