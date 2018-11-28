================
fmgr_secprof_ips
================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_ips:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_IPS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_ips:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_IPS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          block_malicious_url: "enable"
          entries: [{severity: "high", action: "block", log-packet: "enable"}, {severity: "medium", action: "pass"}]



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

