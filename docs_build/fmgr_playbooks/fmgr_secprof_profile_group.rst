==========================
fmgr_secprof_profile_group
==========================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_profile_group:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_TEST_Profile_Group"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_profile_group:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_TEST_Profile_Group"
          mode: "set"
          av_profile: "Ansible_AV_Profile"
          profile_protocol_options: "default"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

