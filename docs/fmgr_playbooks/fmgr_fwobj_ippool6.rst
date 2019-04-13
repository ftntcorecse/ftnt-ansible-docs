==================
fmgr_fwobj_ippool6
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: ADD FMGR_FIREWALL_IPPOOL6
      fmgr_firewall_ippool6:
        mode: "add"
        adom: "ansible"
        startip:
        name: "IPv6 IPPool"
        endip:
        comments: "Created by Ansible"
    
    - name: DELETE FMGR_FIREWALL_IPPOOL6
      fmgr_firewall_ippool6:
        mode: "delete"
        adom: "ansible"
        name: "IPv6 IPPool"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

