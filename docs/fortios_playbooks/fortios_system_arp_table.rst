========================
fortios_system_arp_table
========================


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
      - name: Configure ARP table.
        fortios_system_arp_table:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_arp_table:
            state: "present"
            id:  "3"
            interface: "<your_own_value> (source system.interface.name)"
            ip: "<your_own_value>"
            mac: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_arp_table_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure ARP table.
        fortios_system_arp_table:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_arp_table:
            state: "present"
            id:  "3"
            interface: "<your_own_value> (source system.interface.name)"
            ip: "<your_own_value>"
            mac: "<your_own_value>"




