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


fmgr_fwobj_ippool6_del.yml
++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE FMGR_FIREWALL_IPPOOL6
        fmgr_fwobj_ippool6:
          mode: "delete"
          adom: "ansible"
          name: "IPv6 IPPool"


fmgr_fwobj_ippool6_run_all.sh
+++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_fwobj_ippool6_del.yml -vvvv
    ansible-playbook fmgr_fwobj_ippool6_add.yml -vvvv


fmgr_fwobj_ippool6_add.yml
++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD FMGR_FIREWALL_IPPOOL6
        fmgr_fwobj_ippool6:
          mode: "add"
          adom: "ansible"
          startip: "fd30:fc67:cb18:ae44::aaaa:aaaa"
          name: "IPv6 IPPool"
          endip: "fd30:fc67:cb18:ae44::ffff:ffff"
          comments: "Created by Ansible"




