vm_management
=========

A role for managing Virtual Machines (VMs) on OpenShift Virtualization using the
Ansible Automation Platform (AAP). This role is designed to streamline Day 2
operations for VMs, such as lifecycle management, security patching, dynamic
inventory integration, and backup and restore processes.

Requirements
------------

- Ansible Automation Platform (AAP) controller set up and operational.
- Required execution environment (`Day2 EE`) with the
  `redhat.openshift_virtualization` version >= 2.0.1  and `redhat.openshift` >=3.1.0 collections installed.
- Necessary credentials to access and manage VMs configured in OpenShift within AAP.
- OpenShift cluster with accessible VMs.

Role Variables
--------------

The following variables can be customized to suit your environment and
requirements:

- `vm_name`: Name of the Virtual Machine to manage.
- `vm_namespace`: Namespace where the VM resides.
- `task_file`: The name of the file you wish to run your manage_vm_playbook.yml against

Dependencies
------------

This role depends on the following collections and modules:
- `redhat.openshift_virtualization`
- `redhat.openshift`
- `kubernetes.core`


Example Playbook
----------------

Below is an example playbook demonstrating how to use the `vm_management` role:

```yaml
---
- name: Manage a Virtual Machine
  hosts: localhost
  roles:
    - redhatone.vm_management.vm_management
```

License
-------

BSD

Author Information
------------------

Roger Lopez

