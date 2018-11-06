==========
fmgr_query
==========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: QUERY FORTIGATE DEVICE BY IP
      fmgr_query:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        object: "device"
        adom: "ansible"
        device_ip: "10.7.220.41"
    
    - name: QUERY FORTIGATE DEVICE BY SERIAL
      fmgr_query:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        object: "device"
        device_serial: "FGVM000000117992"
    
    - name: QUERY FORTIGATE DEVICE BY FRIENDLY NAME
      fmgr_query:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        object: "device"
        device_unique_name: "ansible-fgt01"
    
    - name: VERIFY CLUSTER MEMBERS AND STATUS
      fmgr_query:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        object: "cluster_nodes"
        device_unique_name: "fgt-cluster01"
        nodes: ["ansible-fgt01", "ansible-fgt02", "ansible-fgt03"]
    
    - name: GET STATUS OF TASK ID
      fmgr_query:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        object: "task"
        task_id: "3"
    
    - name: USE CUSTOM TYPE TO QUERY AVAILABLE SCRIPTS
      fmgr_query:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        object: "custom"
        custom_endpoint: "/dvmdb/adom/ansible/script"
        custom_dict: { "type": "cli" }



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

