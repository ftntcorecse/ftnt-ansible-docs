===========
fmgr_script
===========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CREATE SCRIPT
      fmgr_script:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        script_name: "TestScript"
        script_type: "cli"
        script_target: "remote_device"
        script_description: "Create by Ansible"
        script_content: "get system status"
    
    - name: EXECUTE SCRIPT
      fmgr_script:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        script_name: "TestScript"
        state: "execute"
        script_scope: "FGT1,FGT2"
    
    - name: DELETE SCRIPT
      fmgr_script:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        script_name: "TestScript"
        state: "delete"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

