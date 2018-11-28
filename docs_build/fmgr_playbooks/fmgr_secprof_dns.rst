================
fmgr_secprof_dns
================


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

%%PB_FILE_EXAMPLE_TOKEN%%

