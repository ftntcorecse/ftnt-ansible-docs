====================
fsm_verify_device_ip
====================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: VERIFY A DEVICE
      fsm_verify_device_ip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        ip_to_verify: "10.0.0.5"
        export_json_to_file_path: "/root/deviceExists.json"
        append_results_to_file: "/root/verification.csv"
    
    - name: TEST VERIFY A DEVICE THAT DOESN'T EXIST
      fsm_verify_device_ip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        ip_to_verify: "10.0.0.45"
        export_json_to_file_path: "/root/deviceNoExist.json"
        append_results_to_file: "/root/verification.csv"
        export_json_to_screen: "enable"
        
    - name: VERIFY A DEVICE FROM A LIST
      fsm_verify_device_ip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        ip_list_to_verify: ["10.0.0.5", "10.0.0.10", "10.0.0.254"]
        export_json_to_file_path: "/root/deviceExistsList.json"
        append_results_to_file: "/root/verificationList.csv"
        
    - name: VERIFY A DEVICE LIST FROM FILE
      fsm_verify_device_ip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        ip_list_file_path: "/root/verify_list.txt"
        export_json_to_file_path: "/root/deviceExists.json"
        append_results_to_file: "/root/verificationList.csv"
    



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

