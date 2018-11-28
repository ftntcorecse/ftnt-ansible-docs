==========================
fortios_system_ipv6_tunnel
==========================


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
      - name: Configure IPv6/IPv4 in IPv6 tunnel.
        fortios_system_ipv6_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ipv6_tunnel:
            state: "present"
            destination: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            name: "default_name_5"
            source: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_ipv6_tunnel_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPv6/IPv4 in IPv6 tunnel.
        fortios_system_ipv6_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ipv6_tunnel:
            state: "present"
            destination: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            name: "default_name_5"
            source: "<your_own_value>"




