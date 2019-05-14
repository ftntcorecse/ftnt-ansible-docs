=================
fsm_organizations
=================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: GET LIST OF ORGS
      fsm_organizations:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
    
    - name: ADD AN ORG WITH COLLECTOR VIA PARAMETERS
      fsm_organizations:
        host: "10.7.220.61"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        mode: "add"
        org_name: "ansibleOrg1"
        org_display_name: "Ansible Test Org 1"
        org_description: "Testing Ansible. Duh."
        org_admin_username: "ansibleTest1"
        org_admin_password: "admin*1"
        org_admin_email: "ansible@test1.com"
        org_eps: "500"
        org_include_ip_range: "192.168.10.1-192.168.10.50"
        org_exclude_ip_range: "192.168.10.51-192.168.10.255"
        org_collector_name: "ansibleOrg1Col1"
        org_collector_eps: "200"
        org_max_devices: 5
    
    - name: ADD AN ORG WITH COLLECTOR VIA JSON
      fsm_organizations:
        host: "10.7.220.61"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        mode: "add"
        org_name: "ansibleOrg2"
        org_display_name: "Ansible Test Org 2"
        org_description: "Testing Ansible. Duh. Again."
        org_admin_username: "ansibleTest2"
        org_admin_password: "admin*1"
        org_admin_email: "ansible@test2.com"
        org_eps: "500"
        org_include_ip_range: "192.168.20.1-192.168.20.50"
        org_exclude_ip_range: "192.168.20.51-192.168.20.255"
        org_collectors: [{'name': 'ansibleOrg2Col1', 'eps': '200'},{'name': 'ansibleOrg2Col2', 'eps': '200'}]
    
    - name: UPDATE AN ORG WITH COLLECTOR VIA PARAMETERS
      fsm_organizations:
        host: "10.7.220.61"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        mode: "update"
        export_json_to_screen: "enable"
        org_name: "ansibleOrg1"
        org_display_name: "Ansible Test Org 1"
        org_description: "Testing Ansible. Duh. Updated."
        org_eps: "400"
        org_include_ip_range: "192.168.10.1-192.168.10.50"
        org_exclude_ip_range: "192.168.10.51-192.168.10.255"
        org_collector_name: "ansibleOrg1Col1"
        org_collector_eps: "100"
      ignore_errors: yes
    
    
    
    - name: UPDATE AN ORG WITH COLLECTOR VIA JSON
      fsm_organizations:
        host: "10.7.220.61"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        mode: "update"
        org_name: "ansibleOrg2"
        org_display_name: "Ansible Test Org 2"
        org_description: "Testing Ansible. Duh. Again. Updated."
        org_eps: "400"
        org_include_ip_range: "192.168.20.1-192.168.20.50"
        org_exclude_ip_range: "192.168.20.51-192.168.20.255"
        org_collectors: [{'name': 'ansibleOrg2Col1', 'eps': '100'},{'name': 'ansibleOrg2Col2', 'eps': '100'}]
      ignore_errors: yes



Playbook File Examples
----------------------


fsm_get_organizations.yml
+++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET LIST OF ORGS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET SIMPLE DEVICE LIST OF ORGS
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "get"

fsm_add_orgs.yml
++++++++++++++++

.. code-block:: yaml



    - name: ADD MSP ORGS
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
        - name: ADD AN ORG WITH COLLECTOR VIA PARAMETERS
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "add"
            org_name: "ansibleOrg1"
            org_display_name: "Ansible Test Org 1"
            org_description: "Testing Ansible. Duh."
            org_admin_username: "ansibleTest1"
            org_admin_password: "admin*1"
            org_admin_email: "ansible@test1.com"
            org_eps: "500"
            org_include_ip_range: "192.168.10.1-192.168.10.50"
            org_exclude_ip_range: "192.168.10.51-192.168.10.255"
            org_collector_name: "ansibleOrg1Col1"
            org_collector_eps: "200"
    
        - name: ADD AN ORG WITH COLLECTOR VIA JSON
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "add"
            org_name: "ansibleOrg2"
            org_display_name: "Ansible Test Org 2"
            org_description: "Testing Ansible. Duh. Again."
            org_admin_username: "ansibleTest2"
            org_admin_password: "admin*1"
            org_admin_email: "ansible@test2.com"
            org_eps: "500"
            org_include_ip_range: "192.168.20.1-192.168.20.50"
            org_exclude_ip_range: "192.168.20.51-192.168.20.255"
            org_collectors: [{'name': 'ansibleOrg2Col1', 'eps': '200'},{'name': 'ansibleOrg2Col2', 'eps': '200'}]
    


fsm_update_orgs.yml
+++++++++++++++++++

.. code-block:: yaml



    - name: ADD ORGS
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
        - name: ADD AN ORG WITH COLLECTOR VIA PARAMETERS
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "update"
            export_json_to_screen: "enable"
            org_name: "ansibleOrg1"
            org_display_name: "Ansible Test Org 1"
            org_description: "Testing Ansible. Duh. Updated."
            org_eps: "400"
            org_include_ip_range: "192.168.10.1-192.168.10.50"
            org_exclude_ip_range: "192.168.10.51-192.168.10.255"
            org_collector_name: "ansibleOrg1Col1"
            org_collector_eps: "100"
          ignore_errors: yes
    
    
    
        - name: ADD AN ORG WITH COLLECTOR VIA JSON
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "update"
            org_name: "ansibleOrg2"
            org_display_name: "Ansible Test Org 2"
            org_description: "Testing Ansible. Duh. Again. Updated."
            org_eps: "400"
            org_include_ip_range: "192.168.20.1-192.168.20.50"
            org_exclude_ip_range: "192.168.20.51-192.168.20.255"
            org_collectors: [{'name': 'ansibleOrg2Col1', 'eps': '100'},{'name': 'ansibleOrg2Col2', 'eps': '100'}]
          ignore_errors: yes


fsm_msp_get_organizations.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET LIST OF ORGS
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET SIMPLE DEVICE LIST OF ORGS
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "get"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/msp_json_test_out_orgs.json"
            export_xml_to_file_path: "/root/msp_xml_test_out_orgs.xml"
    
    
    
        - name: ADD AN ORG WITH COLLECTOR VIA PARAMETERS
          fsm_organizations:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "add"
            org_name: "ansibleOrg1"
            org_display_name: "Ansible Test Org 1"
            org_description: "Testing Ansible. Duh."
            org_admin_username: "ansibleTest1"
            org_admin_password: "admin*1"
            org_admin_email: "ansible@test1.com"
            org_eps: "500"
            org_include_ip_range: "192.168.10.1-192.168.10.50"
            org_exclude_ip_range: "192.168.10.51-192.168.10.255"
            org_collector_name: "ansibleOrg1Col1"
            org_collector_eps: "200"



