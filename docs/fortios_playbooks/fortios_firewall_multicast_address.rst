==================================
fortios_firewall_multicast_address
==================================


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
      - name: Configure multicast addresses.
        fortios_firewall_multicast_address:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_multicast_address:
            state: "present"
            associated-interface: "<your_own_value> (source system.interface.name)"
            color: "4"
            comment: "Comment."
            end-ip: "<your_own_value>"
            name: "default_name_7"
            start-ip: "<your_own_value>"
            subnet: "<your_own_value>"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_12"
                tags:
                 -
                    name: "default_name_14 (source system.object-tagging.tags.name)"
            type: "multicastrange"
            visibility: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_multicast_address_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure multicast addresses.
        fortios_firewall_multicast_address:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_multicast_address:
            state: "present"
            associated-interface: "<your_own_value> (source system.interface.name)"
            color: "4"
            comment: "Comment."
            end-ip: "<your_own_value>"
            name: "default_name_7"
            start-ip: "<your_own_value>"
            subnet: "<your_own_value>"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_12"
                tags:
                 -
                    name: "default_name_14 (source system.object-tagging.tags.name)"
            type: "multicastrange"
            visibility: "enable"




