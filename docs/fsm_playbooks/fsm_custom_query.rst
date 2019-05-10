================
fsm_custom_query
================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SIMPLE CUSTOM QUERY FOR ORGANIZATIONS
      fsm_custom_query:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        mode: "get"
        export_json_to_screen: "enable"
        export_json_to_file_path: "/root/custom_query1.json"
        export_xml_to_file_path: "/root/custom_query1.xml"
        uri: "/phoenix/rest/config/Domain"



Playbook File Examples
----------------------


fsm_custom_query1.yml
+++++++++++++++++++++

.. code-block:: yaml



    - name: CUSTOM QUERIES
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: SIMPLE CUSTOM QUERY TO CMDB
          fsm_custom_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "get"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/custom_query1.json"
            export_xml_to_file_path: "/root/custom_query1.xml"
            uri: "/phoenix/rest/config/Domain"
    




