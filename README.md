# ansible_sap_bone Ansible Collection

## Description

This Ansible Collection executes the installation of SAP Business One on SUSE Linux Enterprise Server

## Requirements
Operating system:
- SUSE Linux Enterprise Server 16 SP1+

## Use Cases
Example playbook:

```
- name: SAP Business One Server Full Setup
  hosts: localhost
  gather_facts: true

  roles:
    - suse.sap_bone.sap_hana_bone_prepare
    - suse.sap_bone.sap_hana_bone_partitioning
    - suse.sap_bone.sap_hana_install
    - suse.sap_bone.sap_bone_install
    - suse.sap_bone.sap_hana_bone_post

  vars:
    sap_hana_bone_disks:
      - /dev/sdb
    sap_hana_install_cleanup_configfile_directory: false
    sap_hana_install_cleanup_extract_directory: false
    sap_hana_install_common_master_password: 'NewPass$321' 
    sap_hana_install_sid: 'H01'
    sap_hana_install_number: '00'
    hostname: "{{ ansible_facts.fqdn }}"
```
