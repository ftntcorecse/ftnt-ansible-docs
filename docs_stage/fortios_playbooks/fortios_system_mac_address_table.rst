================================
fortios_system_mac_address_table
================================


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
      - name: Configure MAC address tables.
        fortios_system_mac_address_table:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_mac_address_table:
            state: "present"
            interface: "<your_own_value> (source system.interface.name)"
            mac: "<your_own_value>"
            reply-substitute: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_mac_address_table_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure MAC address tables.
        fortios_system_mac_address_table:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_mac_address_table:
            state: "present"
            interface: "<your_own_value> (source system.interface.name)"
            mac: "<your_own_value>"
            reply-substitute: "<your_own_value>"




