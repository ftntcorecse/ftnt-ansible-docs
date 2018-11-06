=================
fmgr_secprof_voip
=================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_voip:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_VOIP_Profile"
          mode: "delete"
    
      - name: Create FMGR_VOIP_PROFILE
        fmgr_secprof_voip:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "root"
          name: "Ansible_VOIP_Profile"
          comment: "Created by Ansible"
          sccp: {block-mcast: "enable", log-call-summary: "enable", log-violations: "enable", status: "enable"}



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

