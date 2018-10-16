=================
fmgr_device_group
=================

Not Parsed


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


fmgr_device_groups.yml
++++++++++++++++++++++

.. code-block:: yaml


    - name: CREATE DEVICE GROUP AND ADD MEMBERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
        - name: CREATE DEVICE GROUP
          fmgr_device_group:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            grp_name: "TestGroup"
            grp_desc: "CreatedbyAnsible"
            adom: "ansible"
    
        - name: CREATE DEVICE GROUP
          fmgr_device_group:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            grp_name: "AnsibleGroup"
            grp_desc: "CreatedbyAnsible"
            adom: "ansible"
    
        - name: ADD DEVICES TO DEVICE GROUP
          fmgr_device_group:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            state: "present"
            grp_name: "TestGroup"
            grp_members: "FGT1,FGT2"
            adom: "ansible"
    
        - name: DELETE DEVICE GROUP
          fmgr_device_group:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            grp_name: "AnsibleGroup"
            grp_desc: "CreatedbyAnsible"
            state: "absent"
            adom: "ansible"


fmgr_group_add.yml
++++++++++++++++++

.. code-block:: yaml


    
    - name: CREATE FGT GRP
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: CREATE DEVICE GROUP
        fmgr_device_group:
          #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
          host: "{{ inventory_hostname }}"
          #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
          username: "{{ username }}"
          password: "{{ password }}"
          #NAME OF GROUP YOU WANT TO ADD
          grp_name: "TestGroup"
          #DESCRIPTION TO ADD TO GROUP
          grp_desc: "CreatedbyAnsible"
          #ADOM TO CREATE THE GROUP IN
          adom: "ansible"
          #STATE if "present" add the group, if "absent" delete the GROUP
          state: "present"
    
      - name: CREATE DEVICE GROUP2
        fmgr_device_group:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          grp_name: "testtest"
          grp_desc: "CreatedbyAnsible"
          adom: "ansible"
          state: "present"


fmgr_group_delete.yml
+++++++++++++++++++++

.. code-block:: yaml


    
    - name: REMOVE FGT GRP
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
        - name: DELETE DEVICE GROUP
          fmgr_device_group:
            #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
            host: "{{ inventory_hostname }}"
            #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
            username: "{{ username }}"
            password: "{{ password }}"
            #NAME OF GROUP YOU WANT TO ADD
            grp_name: "TestGroup"
            #DESCRIPTION TO ADD TO GROUP
            grp_desc: "CreatedbyAnsible"
            #STATE if "present" add the group, if "absent" delete the GROUP
            state: "absent"
            #ADOM TO CREATE THE GROUP IN
            adom: "ansible"
    
        - name: DELETE DEVICE GROUP 2
          fmgr_device_group:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            grp_name: "testtest"
            grp_desc: "CreatedbyAnsible"
            state: "absent"
            adom: "ansible"


fmgr_group_edit_add.yml
+++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CREATE FGT GRP
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD DEVICES TO DEVICE GROUP
        fmgr_device_group:
          #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
          host: "{{ inventory_hostname }}"
          #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
          username: "{{ username }}"
          password: "{{ password }}"
          #STATE if "present" ADD THE GROUP MEMBERS, IF "absent" DELETE THE GROUP MEMBERS
          state: "present"
          #GROUP NAME TO ADD THE DEVICES TO
          grp_name: "TestGroup"
          #FRIENDLY NAME OF DEVICES IN FORTIMANAGER YOU WISH TO ADD TO THE GROUP
          #MULTIPLE DEVICES CAN BE SPECIFIED BY COMMA SEPARATION (CSV)
          grp_members: "FGT1,FGT2"
          #ADOM TO CREATE THE GROUP IN
          adom: "ansible"
          vdom: "root"
    
      - name: ADD DEVICES TO DEVICE GROUP 2
        fmgr_device_group:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          state: "present"
          grp_name: "testtest"
          grp_members: "FGT3"
          adom: "ansible"
          vdom: "root"


fmgr_group_edit_remove.yml
++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: REMOVE DEVICES FROM FGT GRP
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
        - name: REMOVE DEVICES FROM DEVICE GROUP
          fmgr_device_group:
            #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
            host: "{{ inventory_hostname }}"
            #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
            username: "{{ username }}"
            password: "{{ password }}"
            #STATE if "present" ADD THE GROUP MEMBERS, IF "absent" DELETE THE GROUP MEMBERS
            state: "absent"
            #GROUP NAME TO REMOVE THE DEVICES FROM
            grp_name: "testtest"
            #FRIENDLY NAME OF DEVICES IN FORTIMANAGER YOU WISH TO DELETE FROM THE GROUP
            #MULTIPLE DEVICES CAN BE SPECIFIED BY COMMA SEPARATION (CSV)
            grp_members: "FGT3"
            #ADOM YOU WISH TO ADD
            adom: "ansible"
    
        - name: REMOVE DEVICES FROM DEVICE GROUP2
          fmgr_device_group:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            state: "absent"
            grp_name: "TestGroup"
            grp_members: "FGT1,FGT2"
            adom: "ansible"




