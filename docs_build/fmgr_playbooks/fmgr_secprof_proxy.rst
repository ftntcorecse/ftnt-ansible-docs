==================
fmgr_secprof_proxy
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_proxy:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_Web_Proxy_Profile"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_proxy:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_Web_Proxy_Profile"
          mode: "set"
          header_client_ip: "pass"
          header_front_end_https: "add"
          header_via_request: "remove"
          header_via_response: "pass"
          header_x_authenticated_groups: "add"
          header_x_authenticated_user: "remove"
          strip_encoding: "enable"
          log_header_change: "enable"
          header_x_forwarded_for: "pass"
          headers_action: "add-to-request"
          headers_content: "test"
          headers_name: "test_header"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

