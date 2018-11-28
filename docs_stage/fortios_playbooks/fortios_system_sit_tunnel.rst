=========================
fortios_system_sit_tunnel
=========================


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
      - name: Configure IPv6 tunnel over IPv4.
        fortios_system_sit_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_sit_tunnel:
            state: "present"
            destination: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            ip6: "<your_own_value>"
            name: "default_name_6"
            source: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_sit_tunnel_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPv6 tunnel over IPv4.
        fortios_system_sit_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_sit_tunnel:
            state: "present"
            destination: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            ip6: "<your_own_value>"
            name: "default_name_6"
            source: "<your_own_value>"




