==========================
fmgr_secprof_profile_group
==========================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_profile_group:
          name: "Ansible_TEST_Profile_Group"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_profile_group:
          name: "Ansible_TEST_Profile_Group"
          mode: "set"
          av_profile: "Ansible_AV_Profile"
          profile_protocol_options: "default"



Playbook File Examples
----------------------


security_profile.yml
++++++++++++++++++++

.. code-block:: yaml



    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE Profile
        fmgr_secprof_profile_group:
          name: "Ansible_TEST_Profile_Group"
          mode: "delete"
    
    
      - name: CREATE Profile
        fmgr_secprof_profile_group:
          name: "Ansible_TEST_Profile_Group"
          mode: "set"
          av_profile: "Ansible_AV_Profile"
          profile_protocol_options: "default"

fmgr_secprof_profile_group_run_all.sh
+++++++++++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook security_profile.yml -vvvv




