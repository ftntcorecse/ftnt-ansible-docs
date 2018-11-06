==================
fmgr_fwpol_package
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CREATE BASIC POLICY PACKAGE
      fmgr_fwpol_package:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        mode: "add"
        name: "testPackage"
        type: "pkg"
    
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
        scope_members: "seattle-fgt02, seattle-fgt03"
    
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
    
    - name: INSTALL PACKAGE
      fmgr_fwpol_package:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        mode: "set"
        adom: "ansible"
        name: "ansibleTestPackage1"
        type: "install"
        scope_members: "seattle-fgt03, seattle-fgt02"
    
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



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

