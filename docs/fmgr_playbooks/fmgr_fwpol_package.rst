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


fmgr_fwpol_package_add.yml
++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
      - name: ADD PACKAGE WITH TARGETS
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "pkg"
          inspection_mode: "flow"
          ngfw_mode: "profile-based"
          scope_members: "FGT2, FGT3"
    
      - name: ADD FOLDER
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          name: "ansibleTestFolder1"
          type: "folder"
    
      - name: ADD PACKAGE INTO PARENT FOLDER
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage2"
          type: "pkg"
          parent_folder: "ansibleTestFolder1"
    
      - name: ADD FOLDER INTO PARENT FOLDER
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          name: "ansibleTestFolder2"
          type: "folder"
          parent_folder: "ansibleTestFolder1"
    
    
    


fmgr_fwpol_package_delete.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
      - name: REMOVE PACKAGE
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "pkg"
    
      - name: REMOVE NESTED PACKAGE
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestPackage2"
          type: "pkg"
          parent_folder: "ansibleTestFolder1"
    
      - name: REMOVE NESTED FOLDER
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder2"
          type: "folder"
          parent_folder: "ansibleTestFolder1"
    
      - name: REMOVE FOLDER
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          name: "ansibleTestFolder1"
          type: "folder"
    
    
    


fmgr_fwpol_package_add_with_rules_install.yml
+++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
      - name: ADD PACKAGE WITH TARGETS
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "pkg"
          inspection_mode: "flow"
          ngfw_mode: "profile-based"
          scope_members: "FGT2, FGT3"
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
        fmgr_fwpol_ipv4:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
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
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "install"
          scope_members: "FGT2, FGT3"

fmgr_fwpol_package_install2vdom.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
      - name: INSTALL PACKAGE
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "install"
          scope_members: "FGT6"
          scope_members_vdom: "ansible1"
    
    


fmgr_fwpol_package_install.yml
++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
      - name: INSTALL PACKAGE
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "install"
          scope_members: "FGT2, FGT3"
    
    


fmgr_fwpol_package_assign2vdom.yml
++++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
      - name: ADD PACKAGE WITH TARGETS
        fmgr_fwpol_package:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          name: "ansibleTestPackage1"
          type: "pkg"
          inspection_mode: "flow"
          ngfw_mode: "profile-based"
          scope_members: "FGT1"
          scope_members_vdom: "ansible1"
    
    
    




