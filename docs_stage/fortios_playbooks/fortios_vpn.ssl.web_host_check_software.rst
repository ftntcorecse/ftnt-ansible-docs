=======================================
fortios_vpn.ssl.web_host_check_software
=======================================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SSL-VPN host check software.
        fortios_vpn.ssl.web_host_check_software:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ssl.web_host_check_software:
            state: "present"
            check-item-list:
             -
                action: "require"
                id:  "5"
                md5s:
                 -
                    id:  "7"
                target: "<your_own_value>"
                type: "file"
                version: "<your_own_value>"
            guid: "<your_own_value>"
            name: "default_name_12"
            os-type: "windows"
            type: "av"
            version: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.ssl.web/fortios_vpn.ssl.web_host_check_software_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SSL-VPN host check software.
        fortios_vpn.ssl.web_host_check_software:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ssl.web_host_check_software:
            state: "present"
            check-item-list:
             -
                action: "require"
                id:  "5"
                md5s:
                 -
                    id:  "7"
                target: "<your_own_value>"
                type: "file"
                version: "<your_own_value>"
            guid: "<your_own_value>"
            name: "default_name_12"
            os-type: "windows"
            type: "av"
            version: "<your_own_value>"




