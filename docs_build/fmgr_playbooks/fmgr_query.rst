==========
fmgr_query
==========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: QUERY FORTIGATE DEVICE BY IP
      fmgr_query:
        object: "device"
        adom: "ansible"
        device_ip: "10.7.220.41"
    
    - name: QUERY FORTIGATE DEVICE BY SERIAL
      fmgr_query:
        adom: "ansible"
        object: "device"
        device_serial: "FGVM000000117992"
    
    - name: QUERY FORTIGATE DEVICE BY FRIENDLY NAME
      fmgr_query:
        adom: "ansible"
        object: "device"
        device_unique_name: "ansible-fgt01"
    
    - name: VERIFY CLUSTER MEMBERS AND STATUS
      fmgr_query:
        adom: "ansible"
        object: "cluster_nodes"
        device_unique_name: "fgt-cluster01"
        nodes: ["ansible-fgt01", "ansible-fgt02", "ansible-fgt03"]
    
    - name: GET STATUS OF TASK ID
      fmgr_query:
        adom: "ansible"
        object: "task"
        task_id: "3"
    
    - name: USE CUSTOM TYPE TO QUERY AVAILABLE SCRIPTS
      fmgr_query:
        adom: "ansible"
        object: "custom"
        custom_endpoint: "/dvmdb/adom/ansible/script"
        custom_dict: { "type": "cli" }



Playbook File Examples
----------------------


fmgr_query_test.yml
+++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICY PACKAGES AND FOLDERS
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    #  - name: QUERY FORTIGATE DEVICE BY IP
    #    fmgr_query:
    #      object: "device"
    #      adom: "ansible"
    #      device_ip: "10.7.220.151"
    
      - name: QUERY FORTIGATE DEVICE BY SERIAL
        fmgr_query:
          adom: "ansible"
          object: "device"
          device_serial: "FGVM04TM18000391"
    
      - name: QUERY FORTIGATE DEVICE BY FRIENDLY NAME
        fmgr_query:
          adom: "ansible"
          object: "device"
          device_unique_name: "FGT3"
    
    #  - name: VERIFY CLUSTER MEMBERS AND STATUS
    #    fmgr_query:
    #      adom: "ansible"
    #      object: "cluster_nodes"
    #      device_unique_name: "nyc-fgt-cluster"
    #      nodes: ["nyc-fgt01", "nyc-fgt02", "nyc-fgt03"]
    
      - name: GET STATUS OF TASK ID
        fmgr_query:
          adom: "ansible"
          object: "task"
          task_id: "247"
    
      - name: USE CUSTOM TYPE TO QUERY AVAILABLE SCRIPTS
        fmgr_query:
          adom: "ansible"
          object: "custom"
          custom_endpoint: "/dvmdb/adom/ansible/script"
          custom_dict: { "type": "cli" }
    
    


fmgr_query_run_all.sh
+++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_query_test.yml -vvvv
    ansible-playbook fmgr_query_run_all.sh -vvvv




