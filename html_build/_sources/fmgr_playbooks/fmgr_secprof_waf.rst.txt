================
fmgr_secprof_waf
================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_waf:
          name: "Ansible_WAF_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_waf:
          name: "Ansible_WAF_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"



Playbook File Examples
----------------------


fmgr_secprof_waf_run_all.sh
+++++++++++++++++++++++++++

.. code-block:: yaml
            #!/bin/bash
    ansible-playbook waf.yml -vvvv


waf.yml
+++++++

.. code-block:: yaml


    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE Profile
        fmgr_secprof_waf:
          name: "Ansible_WAF_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_waf:
          name: "Ansible_WAF_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
    




