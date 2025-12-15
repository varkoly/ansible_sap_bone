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
    - sap_hana_bone_prepare
    - sap_hana_bone_partitioning
    - suse.sap_install.sap_hana_install
    - sap_hana_bone_install

  vars:
    sap_hana_bone_disks:
      - /dev/sdb
    sap_hana_install_cleanup_configfile_directory: false
    sap_hana_install_cleanup_extract_directory: false
    sap_hana_install_common_master_password: 'NewPass$321' 
    sap_hana_install_sid: 'H01'
    sap_hana_install_instance_nr: '00'
    hostname: "{{ ansible_facts.fqdn }}"
```
