=================
fmgr_device_group
=================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CREATE DEVICE GROUP
      fmgr_device_group:
        grp_name: "TestGroup"
        grp_desc: "CreatedbyAnsible"
        adom: "ansible"
        mode: "add"
    
    - name: CREATE DEVICE GROUP 2
      fmgr_device_group:
        grp_name: "AnsibleGroup"
        grp_desc: "CreatedbyAnsible"
        adom: "ansible"
        mode: "add"
    
    - name: ADD DEVICES TO DEVICE GROUP
      fmgr_device_group:
        mode: "add"
        grp_name: "TestGroup"
        grp_members: "FGT1,FGT2"
        adom: "ansible"
        vdom: "root"
    
    - name: REMOVE DEVICES TO DEVICE GROUP
      fmgr_device_group:
        mode: "delete"
        grp_name: "TestGroup"
        grp_members: "FGT1,FGT2"
        adom: "ansible"
    
    - name: DELETE DEVICE GROUP
      fmgr_device_group:
        grp_name: "AnsibleGroup"
        grp_desc: "CreatedbyAnsible"
        mode: "delete"
        adom: "ansible"



Playbook File Examples
----------------------


fmgr_group_delete.yml
+++++++++++++++++++++

.. code-block:: yaml



    
    - name: REMOVE FGT GRP
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DELETE DEVICE GROUP
          fmgr_device_group:
            #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
            #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
            #NAME OF GROUP YOU WANT TO ADD
            grp_name: "TestGroup"
            #DESCRIPTION TO ADD TO GROUP
            grp_desc: "CreatedbyAnsible"
            #STATE if "present" add the group, if "absent" delete the GROUP
            mode: "delete"
            #ADOM TO CREATE THE GROUP IN
            adom: "ansible"
    
        - name: DELETE DEVICE GROUP 2
          fmgr_device_group:
            grp_name: "testtest"
            grp_desc: "CreatedbyAnsible"
            mode: "delete"
            adom: "ansible"


fmgr_group_edit_remove.yml
++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: REMOVE DEVICES FROM FGT GRP
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: REMOVE DEVICES FROM DEVICE GROUP
          fmgr_device_group:
            #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
            #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
            #STATE if "present" ADD THE GROUP MEMBERS, IF "absent" DELETE THE GROUP MEMBERS
            mode: "delete"
            #GROUP NAME TO REMOVE THE DEVICES FROM
            grp_name: "testtest"
            #FRIENDLY NAME OF DEVICES IN FORTIMANAGER YOU WISH TO DELETE FROM THE GROUP
            #MULTIPLE DEVICES CAN BE SPECIFIED BY COMMA SEPARATION (CSV)
            grp_members: "FGT3"
            #ADOM YOU WISH TO ADD
            adom: "ansible"
    
        - name: REMOVE DEVICES FROM DEVICE GROUP2
          fmgr_device_group:
            mode: "delete"
            grp_name: "TestGroup"
            grp_members: "FGT1"
            adom: "ansible"


fmgr_device_groups.yml
++++++++++++++++++++++

.. code-block:: yaml



    - name: CREATE DEVICE GROUP AND ADD MEMBERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: CREATE DEVICE GROUP
          fmgr_device_group:
            grp_name: "TestGroup"
            grp_desc: "CreatedbyAnsible"
            adom: "ansible"
    
        - name: CREATE DEVICE GROUP
          fmgr_device_group:
            grp_name: "AnsibleGroup"
            grp_desc: "CreatedbyAnsible"
            adom: "ansible"
    
        - name: ADD DEVICES TO DEVICE GROUP
          fmgr_device_group:
            mode: "add"
            grp_name: "TestGroup"
            grp_members: "FGT1"
            adom: "ansible"
    
        - name: DELETE DEVICE GROUP
          fmgr_device_group:
            grp_name: "AnsibleGroup"
            grp_desc: "CreatedbyAnsible"
            mode: "delete"
            adom: "ansible"


fmgr_group_edit_add.yml
+++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CREATE FGT GRP
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD DEVICES TO DEVICE GROUP
        fmgr_device_group:
          #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
          #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
          #STATE if "present" ADD THE GROUP MEMBERS, IF "absent" DELETE THE GROUP MEMBERS
          mode: "add"
          #GROUP NAME TO ADD THE DEVICES TO
          grp_name: "TestGroup"
          #FRIENDLY NAME OF DEVICES IN FORTIMANAGER YOU WISH TO ADD TO THE GROUP
          #MULTIPLE DEVICES CAN BE SPECIFIED BY COMMA SEPARATION (CSV)
          grp_members: "FGT1"
          #ADOM TO CREATE THE GROUP IN
          adom: "ansible"
          vdom: "root"
    
      - name: ADD DEVICES TO DEVICE GROUP 2
        fmgr_device_group:
          mode: "add"
          grp_name: "testtest"
          grp_members: "FGT3"
          adom: "ansible"
          vdom: "root"


fmgr_group_add.yml
++++++++++++++++++

.. code-block:: yaml



    
    - name: CREATE FGT GRP
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: CREATE DEVICE GROUP
        fmgr_device_group:
          #GETTING FORTIMANAGER HOST IP OR NAME FROM ANSIBLE INVENTORY FOR HOSTS GROUP ABOVE
          #DYNAMIC MAPPING FOR THE FORTIMANAGER LOGIN AS SPECIFIED IN INVENTORY FILE
          #NAME OF GROUP YOU WANT TO ADD
          grp_name: "TestGroup"
          #DESCRIPTION TO ADD TO GROUP
          grp_desc: "CreatedbyAnsible"
          #ADOM TO CREATE THE GROUP IN
          adom: "ansible"
          #STATE if "present" add the group, if "absent" delete the GROUP
          mode: "add"
    
      - name: CREATE DEVICE GROUP2
        fmgr_device_group:
          grp_name: "testtest"
          grp_desc: "CreatedbyAnsible"
          adom: "ansible"
          mode: "add"


fmgr_device_group_run_all.sh
++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_group_delete.yml -vvvv
    ansible-playbook fmgr_group_edit_remove.yml -vvvv
    ansible-playbook fmgr_device_groups.yml -vvvv
    ansible-playbook fmgr_group_edit_add.yml -vvvv
    ansible-playbook fmgr_group_add.yml -vvvv




