=================
fmgr_provisioning
=================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: Create FGT1 Model Device
      fmgr_provisioning:
        adom: "root"
        vdom: "root"
        policy_package: "default"
        name: "FGT1"
        group: "Ansible"
        serial: "FGVM000000117994"
        platform: "FortiGate-VM64"
        description: "Provisioned by Ansible"
        os_version: '6.0'
        minor_release: 0
        patch_release: 0
        os_type: 'fos'
    
    
    - name: Create FGT2 Model Device
      fmgr_provisioning:
        adom: "root"
        vdom: "root"
        policy_package: "test_pp"
        name: "FGT2"
        group: "Ansible"
        serial: "FGVM000000117992"
        platform: "FortiGate-VM64"
        description: "Provisioned by Ansible"
        os_version: '5.0'
        minor_release: 6
        patch_release: 0
        os_type: 'fos'
    



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

