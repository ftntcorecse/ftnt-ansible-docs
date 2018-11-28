=============================
fortios_system_dedicated_mgmt
=============================


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
      - name: Configure dedicated management.
        fortios_system_dedicated_mgmt:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dedicated_mgmt:
            default-gateway: "<your_own_value>"
            dhcp-end-ip: "<your_own_value>"
            dhcp-netmask: "<your_own_value>"
            dhcp-server: "enable"
            dhcp-start-ip: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_dedicated_mgmt_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure dedicated management.
        fortios_system_dedicated_mgmt:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dedicated_mgmt:
            default-gateway: "<your_own_value>"
            dhcp-end-ip: "<your_own_value>"
            dhcp-netmask: "<your_own_value>"
            dhcp-server: "enable"
            dhcp-start-ip: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            status: "enable"




