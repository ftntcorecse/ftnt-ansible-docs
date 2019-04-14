===========
fmgr_script
===========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CREATE SCRIPT
      fmgr_script:
        adom: "root"
        script_name: "TestScript"
        script_type: "cli"
        script_target: "remote_device"
        script_description: "Create by Ansible"
        script_content: "get system status"
    
    - name: EXECUTE SCRIPT
      fmgr_script:
        adom: "root"
        script_name: "TestScript"
        mode: "execute"
        script_scope: "FGT1,FGT2"
    
    - name: DELETE SCRIPT
      fmgr_script:
        adom: "root"
        script_name: "TestScript"
        mode: "delete"



Playbook File Examples
----------------------


fmgr_faz_scripts.yml
++++++++++++++++++++

.. code-block:: yaml


    - name: CREATE AND EXECUTE SCRIPTS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: CREATE SCRIPT
          fmgr_script:
            adom: "ansible"
            script_name: "faz_init"
            script_type: "cli"
            script_target: "remote_device"
            script_description: "Created by Ansible"
            script_content: "config log fortianalyzer setting \n
                              set status enable \n
                              set server 10.7.220.38 \n
                              set upload-option realtime \n
                              set reliable enable \n
                              end \n"
    
        - name: EXECUTE SCRIPT
          fmgr_script:
            adom: "ansible"
            script_name: "faz_init"
            mode: "execute"
            script_scope: "FGT1"


fmgr_script_run_all.sh
++++++++++++++++++++++

.. code-block:: yaml
            #!/bin/bash
    ansible-playbook fmgr_faz_scripts.yml -vvvv
    ansible-playbook fmgr_script_run_all.sh -vvvv
    ansible-playbook fmgr_scripts.yml -vvvv


fmgr_scripts.yml
++++++++++++++++

.. code-block:: yaml


    - name: CREATE AND EXECUTE SCRIPTS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: CREATE SCRIPT
          fmgr_script:
            adom: "ansible"
            script_name: "TestScript"
            script_type: "cli"
            script_target: "remote_device"
            script_description: "Create by Ansible"
            script_content: "get system status"
    
        - name: EXECUTE SCRIPT
          fmgr_script:
            adom: "ansible"
            script_name: "TestScript"
            mode: "execute"
            script_scope: "FGT1"
    
        - name: DELETE SCRIPT
          fmgr_script:
            adom: "ansible"
            script_name: "TestScript"
            mode: "delete"




