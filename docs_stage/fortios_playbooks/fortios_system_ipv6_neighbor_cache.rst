==================================
fortios_system_ipv6_neighbor_cache
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
      - name: Configure IPv6 neighbor cache table.
        fortios_system_ipv6_neighbor_cache:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ipv6_neighbor_cache:
            state: "present"
            id:  "3"
            interface: "<your_own_value> (source system.interface.name)"
            ipv6: "<your_own_value>"
            mac: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_ipv6_neighbor_cache_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPv6 neighbor cache table.
        fortios_system_ipv6_neighbor_cache:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ipv6_neighbor_cache:
            state: "present"
            id:  "3"
            interface: "<your_own_value> (source system.interface.name)"
            ipv6: "<your_own_value>"
            mac: "<your_own_value>"




