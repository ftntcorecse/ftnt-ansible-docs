===================
fsm_device_monitors
===================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: GET SIMPLE MONITOR LIST FROM CMDB
      fsm_device_monitors:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        mode: "short_all"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/monitors_out1.json"
        export_xml_to_file_path: "/root/monitors_out1.xml"
    
    - name: GET SIMPLE MONITOR LIST FROM CMDB IP RANGE
      fsm_device_monitors:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        mode: "ip_range"
        ip_range: "10.0.0.5-10.0.0.15"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/monitors_out2.json"
        export_xml_to_file_path: "/root/monitors_out2.xml"
    
    - name: GET DETAILED MONITOR INFO ON ONE DEVICE
      fsm_device_monitors:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        mode: "detailed_single"
        ip: "10.0.0.5"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/monitors_out3.json"
        export_xml_to_file_path: "/root/monitors_out3.xml"



Playbook File Examples
----------------------


enable_monitors.xml
+++++++++++++++++++

.. code-block:: xml

           <configureMonitoring>
        <systemMonitors>
            <systemMonitor ip = "10.0.0.5" method = "SNMP" type = "CPU Util" enable = "true" interval = "120"/>
            <systemMonitor ip = "10.0.0.5" method = "VMSDK" type = "VMware Hardware Status" enable = "true" interval = "120"/>
        </systemMonitors>
        <eventPullingObjs>
            <eventPullingObj ip="10.0.0.10" method="VM_SDK" enable="true"/>
            <eventPullingObj ip="10.0.0.138" method="MS_WMI" enable="true"/>
        </eventPullingObjs>
    </configureMonitoring>

disable_monitors.xml
++++++++++++++++++++

.. code-block:: xml

           <configureMonitoring>
        <systemMonitors>
            <systemMonitor ip = "10.0.0.5" method = "SNMP" type = "CPU Util" enable = "false" interval = "120"/>
            <systemMonitor ip = "10.0.0.5" method = "VMSDK" type = "VMware Hardware Status" enable = "false" interval = "120"/>
        </systemMonitors>
        <eventPullingObjs>
            <eventPullingObj ip="10.0.0.10" method="VM_SDK" enable="false"/>
            <eventPullingObj ip="10.0.0.138" method="MS_WMI" enable="false"/>
        </eventPullingObjs>
    </configureMonitoring>

fsm_get_monitors.yml
++++++++++++++++++++

.. code-block:: yaml



    - name: GET DEVICE MONITORS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET SIMPLE MONITOR LIST FROM CMDB
          fsm_device_monitors:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "short_all"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/monitors_out1.json"
            export_xml_to_file_path: "/root/monitors_out1.xml"
    
        - name: GET SIMPLE MONITOR LIST FROM CMDB IP RANGE
          fsm_device_monitors:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "ip_range"
            ip_range: "10.0.0.5-10.0.0.15"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/monitors_out2.json"
            export_xml_to_file_path: "/root/monitors_out2.xml"
    
        - name: GET DETAILED MONITOR INFO ON ONE DEVICE
          fsm_device_monitors:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "detailed_single"
            ip: "10.0.0.5"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/monitors_out3.json"
            export_xml_to_file_path: "/root/monitors_out3.xml"


fsm_update_monitors.yml
+++++++++++++++++++++++

.. code-block:: yaml



    - name: GET DEVICE MONITORS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: DISABLE MONITORS
          fsm_device_monitors:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "update"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/disable_monitors.json"
            export_xml_to_file_path: "/root/disable_monitors.xml"
            update_xml_file: "/root/git/dev_queue/examples/fsm_device_monitors/disable_monitors.xml"
    
    #    - name: ENABLE MONITORS
    #      fsm_device_monitors:
    #        host: "{{ inventory_hostname }}"
    #        username: "{{ username }}"
    #        password: "{{ password }}"
    #        ignore_ssl_errors: "enable"
    #        mode: "update"
    #        export_json_to_screen: "enable"
    #        export_json_to_file_path: "/root/enable_monitors.json"
    #        export_xml_to_file_path: "/root/enable_monitors.xml"
    #        update_xml_file: "/root/git/dev_queue/examples/fsm_device_monitors/enable_monitors.xml"



