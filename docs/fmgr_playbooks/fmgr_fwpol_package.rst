==================
fmgr_fwpol_package
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CREATE BASIC POLICY PACKAGE
      fmgr_fwpol_package:
        adom: "ansible"
        mode: "add"
        name: "testPackage"
        object_type: "pkg"
    
    - name: ADD PACKAGE WITH TARGETS
      fmgr_fwpol_package:
        mode: "add"
        adom: "ansible"
        name: "ansibleTestPackage1"
        object_type: "pkg"
        inspection_mode: "flow"
        ngfw_mode: "profile-based"
        scope_members: "seattle-fgt02, seattle-fgt03"
    
    - name: ADD FOLDER
      fmgr_fwpol_package:
        mode: "add"
        adom: "ansible"
        name: "ansibleTestFolder1"
        object_type: "folder"
    
    - name: ADD PACKAGE INTO PARENT FOLDER
      fmgr_fwpol_package:
        mode: "set"
        adom: "ansible"
        name: "ansibleTestPackage2"
        object_type: "pkg"
        parent_folder: "ansibleTestFolder1"
    
    - name: ADD FOLDER INTO PARENT FOLDER
      fmgr_fwpol_package:
        mode: "set"
        adom: "ansible"
        name: "ansibleTestFolder2"
        object_type: "folder"
        parent_folder: "ansibleTestFolder1"
    
    - name: INSTALL PACKAGE
      fmgr_fwpol_package:
        mode: "install"
        adom: "ansible"
        name: "ansibleTestPackage1"
    
    - name: REMOVE PACKAGE
      fmgr_fwpol_package:
        mode: "delete"
        adom: "ansible"
        name: "ansibleTestPackage1"
        object_type: "pkg"
    
    - name: REMOVE NESTED PACKAGE
      fmgr_fwpol_package:
        mode: "delete"
        adom: "ansible"
        name: "ansibleTestPackage2"
        object_type: "pkg"
        parent_folder: "ansibleTestFolder1"
    
    - name: REMOVE NESTED FOLDER
      fmgr_fwpol_package:
        mode: "delete"
        adom: "ansible"
        name: "ansibleTestFolder2"
        object_type: "folder"
        parent_folder: "ansibleTestFolder1"
    
    - name: REMOVE FOLDER
      fmgr_fwpol_package:
        mode: "delete"
        adom: "ansible"
        name: "ansibleTestFolder1"
        object_type: "folder"



Playbook File Examples
----------------------


fmgr_fwpol_plugin_install.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: INSTALL PACKAGE 1
        fmgr_fwpol_package:
          mode: "install"
          object_type: "pkg"
          adom: "ansible"
          name: "ansibleTestPackage1"
    
      - name: INSTALL PACKAGE 2
        fmgr_fwpol_package:
          mode: "install"
          object_type: "pkg"
          adom: "ansible"
          name: "ansibleTestPackage2"
          parent_folder: "ansibleTestFolder1"
    #
      - name: INSTALL PACKAGE 3
        fmgr_fwpol_package:
          mode: "install"
          object_type: "pkg"
          adom: "ansible"
          name: "ansibleTestPackage3"
          parent_folder: "ansibleTestFolder1/ansibleTestFolder2"

fmgr_fwpol_package_run_all.sh
+++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_fwpol_plugin_install.yml -vvvv
    ansible-playbook fmgr_fwpol_package_add.yml -vvvv
    ansible-playbook fmgr_fwpol_package_delete.yml -vvvv
    ansible-playbook fmgr_fwpol_package_add_with_rules_install.yml -vvvv
    ansible-playbook fmgr_fwpol_plugin_del.yml -vvvv
    ansible-playbook fmgr_fwpol_package_install2vdom.yml -vvvv
    ansible-playbook fmgr_fwpol_package_install.yml -vvvv
    ansible-playbook fmgr_fwpol_package_assign2vdom.yml -vvvv
    ansible-playbook fmgr_fwpol_plugin_add.yml -vvvv


fmgr_fwpol_package_add.yml
++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: ADD PACKAGE WITH TARGETS
        fmgr_fwpol_package:
          mode: "add"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "pkg"
          inspection_mode: "flow"
          ngfw_mode: "profile-based"
          scope_members: "FGT2, FGT3"
    
      - name: ADD FOLDER
        fmgr_fwpol_package:
          mode: "add"
          adom: "ansible"
          name: "ansibleTestFolder1"
          object_type: "folder"
    
      - name: ADD PACKAGE INTO PARENT FOLDER
        fmgr_fwpol_package:
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage2"
          object_type: "pkg"
          parent_folder: "ansibleTestFolder1"
    
      - name: ADD FOLDER INTO PARENT FOLDER
        fmgr_fwpol_package:
          mode: "set"
          adom: "ansible"
          name: "ansibleTestFolder2"
          object_type: "folder"
          parent_folder: "ansibleTestFolder1"
    
    
    


fmgr_fwpol_package_delete.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: REMOVE PACKAGE
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "pkg"
    
      - name: REMOVE NESTED PACKAGE
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage2"
          object_type: "pkg"
          parent_folder: "ansibleTestFolder1"
    
      - name: REMOVE NESTED FOLDER
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder2"
          object_type: "folder"
          parent_folder: "ansibleTestFolder1"
    
      - name: REMOVE FOLDER
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder1"
          object_type: "folder"
    
    
    


fmgr_fwpol_package_add_with_rules_install.yml
+++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: ADD PACKAGE WITH TARGETS
        fmgr_fwpol_package:
          mode: "add"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "pkg"
          inspection_mode: "flow"
          ngfw_mode: "profile-based"
          scope_members: "FGT2, FGT3"
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
        fmgr_fwpol_ipv4:
          mode: "set"
          adom: "ansible"
          package_name: "ansibleTestPackage1"
          name: "ansibleTestRule1"
          action: "accept"
          dstaddr: "all"
          srcaddr: "all"
          dstintf: "any"
          srcintf: "any"
          logtraffic: "utm"
          service: "ALL"
          schedule: "always"
    
      - name: INSTALL PACKAGE
        fmgr_fwpol_package:
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "install"
          scope_members: "FGT2, FGT3"

fmgr_fwpol_plugin_del.yml
+++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: DELETE ROOT PACKAGE
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "pkg"
        ignore_errors: yes
    
      - name: REMOVE NESTED PACKAGE
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage2"
          object_type: "pkg"
          parent_folder: "ansibleTestFolder1"
        ignore_errors: yes
    
      - name: REMOVE NESTED PACKAGE 2
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage3"
          object_type: "pkg"
          parent_folder: "ansibleTestFolder1/ansibleTestFolder2"
        ignore_errors: yes
    
      - name: REMOVE NESTED PACKAGE 3
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage4"
          object_type: "pkg"
          parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3"
        ignore_errors: yes
    
      - name: REMOVE NESTED PACKAGE 4
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage5"
          object_type: "pkg"
          parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3/ansibleTestFolder4"
        ignore_errors: yes
    
      - name: REMOVE NESTED FOLDER 3
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder4"
          object_type: "folder"
          parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3"
        ignore_errors: yes
    
      - name: REMOVE NESTED FOLDER 3
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder3"
          object_type: "folder"
          parent_folder: "ansibleTestFolder1/ansibleTestFolder2"
        ignore_errors: yes
    
      - name: REMOVE NESTED FOLDER 2
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder2"
          object_type: "folder"
          parent_folder: "ansibleTestFolder1"
        ignore_errors: yes
    
      - name: REMOVE FOLDER
        fmgr_fwpol_package:
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder1"
          object_type: "folder"
        ignore_errors: yes

fmgr_fwpol_package_install2vdom.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: INSTALL PACKAGE
        fmgr_fwpol_package:
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "install"
          scope_members: "FGT6"
          scope_members_vdom: "ansible1"
    
    


fmgr_fwpol_package_install.yml
++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: INSTALL PACKAGE
        fmgr_fwpol_package:
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "install"
          scope_members: "FGT2, FGT3"
    
    


fmgr_fwpol_package_assign2vdom.yml
++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
      - name: ADD PACKAGE WITH TARGETS
        fmgr_fwpol_package:
          mode: "add"
          adom: "ansible"
          name: "ansibleTestPackage1"
          object_type: "pkg"
          inspection_mode: "flow"
          ngfw_mode: "profile-based"
          scope_members: "FGT1"
          scope_members_vdom: "ansible1"
    
    
    


fmgr_fwpol_plugin_add.yml
+++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      vars:
        json_dump: "True"
      connection: httpapi
      gather_facts: False
    
      tasks:
    #  - name: ADD PACKAGE WITH TARGETS
    #    fmgr_fwpol_package:
    #      mode: "add"
    #      adom: "ansible"
    #      name: "ansibleTestPackage1"
    #      object_type: "pkg"
    #      inspection_mode: "flow"
    #      ngfw_mode: "profile-based"
    #      scope_members: "FGT2, FGT3"
    #      scope_groups: "TestGroup"
    #
    #  - name: ADD PACKAGE MEMBERS
    #    fmgr_fwpol_package:
    #      mode: "add_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage1"
    #      object_type: "pkg"
    #      scope_members: "FGT1"
    #      scope_groups: "testtest"
    #
    #  - name: REMOVE PACKAGE MEMBERS
    #    fmgr_fwpol_package:
    #      mode: "delete_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage1"
    #      object_type: "pkg"
    #      scope_members: "FGT2"
    #      scope_groups: "TestGroup"
    #
    #  - name: ADD PACKAGE WITH TARGET GROUP
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestPackage1"
    #      object_type: "pkg"
    #      inspection_mode: "flow"
    #      ngfw_mode: "profile-based"
    #      scope_groups: "TestGroup"
    #
      - name: ADD FOLDER
        fmgr_fwpol_package:
          mode: "set"
          adom: "ansible"
          name: "ansibleTestFolder1"
          object_type: "folder"
    
    #  - name: ADD SECOND LEVEL FOLDER INTO PARENT FOLDER
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestFolder2"
    #      object_type: "folder"
    #      parent_folder: "ansibleTestFolder1"
    #
    #  - name: ADD THIRD LEVEL NESTED FOLDER
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestFolder3"
    #      object_type: "folder"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2"
    #
    #  - name: ADD FOURTH LEVEL NESTED FOLDER
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestFolder4"
    #      object_type: "folder"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3"
    #
    #  - name: ADD PACKAGE INTO PARENT FOLDER 2
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestPackage2"
    #      object_type: "pkg"
    #      parent_folder: "ansibleTestFolder1"
    #      inspection_mode: "flow"
    #      ngfw_mode: "profile-based"
    #      scope_members: "FGT2, FGT3"
    #      scope_groups: "TestGroup"
    #
    #  - name: ADD PACKAGE MEMBERS 2
    #    fmgr_fwpol_package:
    #      mode: "add_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage2"
    #      object_type: "pkg"
    #      scope_members: "FGT1, FGT2, FGT3"
    #      scope_groups: "testtest, TestGroup"
    #      parent_folder: "ansibleTestFolder1"
    #
    #  - name: REMOVE PACKAGE MEMBERS 2
    #    fmgr_fwpol_package:
    #      mode: "delete_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage2"
    #      object_type: "pkg"
    #      scope_members: "FGT2"
    #      scope_groups: "TestGroup"
    #      parent_folder: "ansibleTestFolder1"
    #
    #
    #  - name: ADD PACKAGE INTO CHILD FOLDER 3
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestPackage3"
    #      object_type: "pkg"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2"
    #      inspection_mode: "flow"
    #      ngfw_mode: "profile-based"
    #      scope_members: "FGT2, FGT3"
    #      scope_groups: "TestGroup"
    #
    #  - name: ADD NESTED PACKAGE MEMBERS 3
    #    fmgr_fwpol_package:
    #      mode: "add_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage3"
    #      object_type: "pkg"
    #      scope_members: "FGT1, FGT2, FGT3"
    #      scope_groups: "testtest, TestGroup"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2"
    #
    #  - name: REMOVE NESTED PACKAGE MEMBERS 3
    #    fmgr_fwpol_package:
    #      mode: "delete_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage3"
    #      object_type: "pkg"
    #      scope_members: "FGT2"
    #      scope_groups: "TestGroup"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2"
    #
    #  - name: ADD PACKAGE INTO CHILD FOLDER 4
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestPackage4"
    #      object_type: "pkg"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3"
    #      inspection_mode: "flow"
    #      ngfw_mode: "profile-based"
    #      scope_members: "FGT2, FGT3"
    #      scope_groups: "TestGroup"
    #
    #  - name: ADD NESTED PACKAGE MEMBERS 4
    #    fmgr_fwpol_package:
    #      mode: "add_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage4"
    #      object_type: "pkg"
    #      scope_members: "FGT1, FGT2, FGT3"
    #      scope_groups: "testtest, TestGroup"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3"
    #
    #  - name: REMOVE NESTED PACKAGE MEMBERS 4
    #    fmgr_fwpol_package:
    #      mode: "delete_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage4"
    #      object_type: "pkg"
    #      scope_members: "FGT2"
    #      scope_groups: "TestGroup"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3"
    #
    #
    #  - name: ADD PACKAGE INTO CHILD FOLDER 5
    #    fmgr_fwpol_package:
    #      mode: "set"
    #      adom: "ansible"
    #      name: "ansibleTestPackage5"
    #      object_type: "pkg"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3/ansibleTestFolder4"
    #      inspection_mode: "flow"
    #      ngfw_mode: "profile-based"
    #      scope_members: "FGT2, FGT3"
    #      scope_groups: "TestGroup"
    #
    #  - name: ADD NESTED PACKAGE MEMBERS 5
    #    fmgr_fwpol_package:
    #      mode: "add_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage5"
    #      object_type: "pkg"
    #      scope_members: "FGT1, FGT2, FGT3"
    #      scope_groups: "testtest, TestGroup"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3/ansibleTestFolder4"
    #
    #  - name: REMOVE NESTED PACKAGE MEMBERS 5
    #    fmgr_fwpol_package:
    #      mode: "delete_targets"
    #      adom: "ansible"
    #      name: "ansibleTestPackage5"
    #      object_type: "pkg"
    #      scope_members: "FGT2"
    #      scope_groups: "TestGroup"
    #      parent_folder: "ansibleTestFolder1/ansibleTestFolder2/ansibleTestFolder3/ansibleTestFolder4"



