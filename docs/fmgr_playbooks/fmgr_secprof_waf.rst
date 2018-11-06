================
fmgr_secprof_waf
================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_waf:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_WAF_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_waf:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_WAF_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

