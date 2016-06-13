ansible-role-tripleo-inventory
==============================

Creates a new inventory file for Ansible from the hosts in memory. This allows
consecutive runs of Ansible with the same set of hosts.

Requirements
------------

None.

Role Variables
--------------

* `local_working_dir` -- working directory on the slave running the playbook,
  defaults to `$HOME/.quickstart`
* `working_dir` -- working directory on the virthost, default to /home/stack
* `undercloud_key` -- ssh key used to access the undercloud machine
* `inventory` -- `undercloud` if the overcloud has not been deployed yet
  (default), or `full` in case we want to inventory all the hosts

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- name:  Inventory the overcloud
  hosts: undercloud
  gather_facts: yes
  vars:
      inventory: all
  roles:
    - tripleo-inventory
```

License
-------

Apache

Author Information
------------------

RDO-CI Team
