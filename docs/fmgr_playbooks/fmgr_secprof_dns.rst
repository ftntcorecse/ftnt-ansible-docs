================
fmgr_secprof_dns
================

Not Parsed


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_dns:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_DNS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_dns:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_DNS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          block_action: "block"
    
    



Playbook File Examples
----------------------


dns.yml
+++++++

.. code-block:: yaml


    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: DELETE Profile
        fmgr_secprof_dns:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_DNS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
    
      - name: CREATE Profile
        fmgr_secprof_dns:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_DNS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          block_action: "block"




