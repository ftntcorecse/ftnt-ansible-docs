=================
fmgr_device_group
=================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CREATE DEVICE GROUP
      fmgr_device_group:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        grp_name: "TestGroup"
        grp_desc: "CreatedbyAnsible"
        adom: "ansible"
        state: "present"
    
    - name: CREATE DEVICE GROUP 2
      fmgr_device_group:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        grp_name: "AnsibleGroup"
        grp_desc: "CreatedbyAnsible"
        adom: "ansible"
        state: "present"
    
    - name: ADD DEVICES TO DEVICE GROUP
      fmgr_device_group:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        state: "present"
        grp_name: "TestGroup"
        grp_members: "FGT1,FGT2"
        adom: "ansible"
        vdom: "root"
    
    - name: REMOVE DEVICES TO DEVICE GROUP
      fmgr_device_group:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        state: "absent"
        grp_name: "TestGroup"
        grp_members: "FGT1,FGT2"
        adom: "ansible"
    
    - name: DELETE DEVICE GROUP
      fmgr_device_group:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        grp_name: "AnsibleGroup"
        grp_desc: "CreatedbyAnsible"
        state: "absent"
        adom: "ansible"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

