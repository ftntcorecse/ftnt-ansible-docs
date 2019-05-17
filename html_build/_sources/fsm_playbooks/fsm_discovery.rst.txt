=============
fsm_discovery
=============


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SUBMIT RANGE SCAN FOR SINGLE DEVICE
      fsm_discovery:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/range_scan.json"
        export_xml_to_file_path: "/root/range_scan.xml"
        type: "RangeScan"
        include_range: "10.0.0.254"
    
    - name: SUBMIT RANGE SCAN FOR SINGLE DEVICE AND WAIT FOR FINISH WITH MANY OPTIONS
      fsm_discovery:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/range_scan2.json"
        export_xml_to_file_path: "/root/range_scan2.xml"
        type: "RangeScan"
        include_range: "10.0.0.5-10.0.0.20"
        wait_to_finish: True
        only_ping: False
        vm_off: True
        unmanaged: True
        delta: True
        name_resolution_dns_first: False
        winexe_based: True
        vm_templates: True
        discover_routes: True
        monitor_win_events: False
        monitor_win_patches: False
        monitor_installed_sw: False
    
    - name: SUBMIT RANGE SCAN FOR SINGLE DEVICE AND WAIT FOR FINISH WITH NO PING
      fsm_discovery:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/json_test_out.json"
        export_xml_to_file_path: "/root/xml_test_out.xml"
        type: "RangeScan"
        include_range: "10.0.0.5-10.0.0.50"
        wait_to_finish: True
        no_ping: True
    
    
    - name: SUBMIT RANGE SCAN FOR RANGE OF DEVICES
      fsm_discovery:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/json_test_out.json"
        export_xml_to_file_path: "/root/xml_test_out.xml"
        type: "RangeScan"
        include_range: "10.0.0.1-10.0.0.10"
        exclude_range: "10.0.0.5-10.0.0.6"
    
    - name: SUBMIT SMART SCAN
      fsm_discovery:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/json_test_out.json"
        export_xml_to_file_path: "/root/xml_test_out.xml"
        type: "SmartScan"
        root_ip: "10.0.0.254"
    
    - name: SUBMIT L2SCAN
      fsm_discovery:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/json_test_out.json"
        export_xml_to_file_path: "/root/xml_test_out.xml"
        type: "L2Scan"
        include_range: "10.0.0.1-10.0.0.254"



Playbook File Examples
----------------------


fsm_discovery_add.yml
+++++++++++++++++++++

.. code-block:: yaml



    - name: SUBMIT DISCOVERY JOBS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: SUBMIT RANGE SCAN FOR SINGLE DEVICE
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/range_scan.json"
            export_xml_to_file_path: "/root/range_scan.xml"
            type: "RangeScan"
            include_range: "10.0.0.254"
    
        - name: SUBMIT RANGE SCAN FOR SINGLE DEVICE AND WAIT FOR FINISH WITH MANY OPTIONS
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/range1_scan_opt.json"
            export_xml_to_file_path: "/root/range1_scan_opt.xml"
            type: "RangeScan"
            include_range: "10.0.0.5-10.0.0.20"
            wait_to_finish: True
            only_ping: False
            vm_off: True
            unmanaged: True
            delta: True
            name_resolution_dns_first: False
            winexe_based: True
            vm_templates: True
            discover_routes: True
            monitor_win_events: False
            monitor_win_patches: False
            monitor_installed_sw: False
    
        - name: SUBMIT RANGE SCAN FOR SINGLE DEVICE AND WAIT FOR FINISH WITH NO PING
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/range_scan_no_ping.json"
            export_xml_to_file_path: "/root/range_scan_no_ping.xml"
            type: "RangeScan"
            include_range: "10.0.0.5-10.0.0.50"
            wait_to_finish: True
            no_ping: True
    
    
        - name: SUBMIT RANGE SCAN FOR RANGE OF DEVICES
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/range_scan_range.json"
            export_xml_to_file_path: "/root/range_scan_range.xml"
            type: "RangeScan"
            include_range: "10.0.0.1-10.0.0.10"
            exclude_range: "10.0.0.5-10.0.0.6"
    
        - name: SUBMIT SMART SCAN
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/smart_scan_01.json"
            export_xml_to_file_path: "/root/smart_scan_01.xml"
            type: "SmartScan"
            root_ip: "10.0.0.254"
    
        - name: SUBMIT L2SCAN
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/l2scan.json"
            export_xml_to_file_path: "/root/l2scan.xml"
            type: "L2Scan"
            include_range: "10.0.0.1-10.0.0.254"

fsm_discovery_status.yml
++++++++++++++++++++++++

.. code-block:: yaml



    - name: STATUS DISCOVERY JOBS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET STATUS FOR A DISCOVERY
          fsm_discovery:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/disco_status.json"
            export_xml_to_file_path: "/root/disco_status.xml"
            type: "status"
            task_id: "2508033"




