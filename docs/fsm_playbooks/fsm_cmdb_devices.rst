================
fsm_cmdb_devices
================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: GET SIMPLE DEVICE LIST FROM CMDB
      fsm_cmdb_devices:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        mode: "short_all"
    
    - name: GET SIMPLE DEVICE LIST FROM CMDB IP RANGE
      fsm_cmdb_devices:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        mode: "ip_range"
        ip_range: "10.0.0.100-10.0.0.120"
    
    - name: GET DETAILED INFO ON ONE DEVICE
      fsm_cmdb_devices:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        mode: "detailed_single"
        ip: "10.0.0.5"
      
    



Playbook File Examples
----------------------


fsm_get_cmdb_devices_simple.yml
+++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET CMDB DEVICES
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET SIMPLE DEVICE LIST FROM CMDB
          fsm_cmdb_devices:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "short_all"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/simple_cmdb_list.json"
            export_xml_to_file_path: "/root/simple_cmdb_list.xml"
    
        - name: GET SIMPLE DEVICE LIST FROM CMDB IP RANGE
          fsm_cmdb_devices:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "ip_range"
            ip_range: "10.0.0.100-10.0.0.120"
    
        - name: GET DETAILED INFO ON ONE DEVICE
          fsm_cmdb_devices:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "detailed_single"
            ip: "10.0.0.5"

fsm_msp_get_cmdb_devices_simple.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET MSP CMDB DEVICES
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET MSP SIMPLE DEVICE LIST FROM CMDB
          fsm_cmdb_devices:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "short_all"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/msp_testOrg_simpleDeviceList.json"
            export_xml_to_file_path: "/root/msp_testOrg_xml_simpleDeviceList.xml"
    
    
        - name: GET MSP SIMPLE DEVICE LIST FROM CMDB IP RANGE
          fsm_cmdb_devices:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "ip_range"
            ip_range: "10.0.0.1-10.0.0.255"
    
        - name: GET MSP DETAILED INFO ON ONE DEVICE
          fsm_cmdb_devices:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "detailed_single"
            ip: "10.7.220.34"



