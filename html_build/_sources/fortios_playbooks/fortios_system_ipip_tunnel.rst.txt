==========================
fortios_system_ipip_tunnel
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
      - name: Configure IP in IP Tunneling.
        fortios_system_ipip_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ipip_tunnel:
            state: "present"
            interface: "<your_own_value> (source system.interface.name)"
            local-gw: "<your_own_value>"
            name: "default_name_5"
            remote-gw: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_ipip_tunnel_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IP in IP Tunneling.
        fortios_system_ipip_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ipip_tunnel:
            state: "present"
            interface: "<your_own_value> (source system.interface.name)"
            local-gw: "<your_own_value>"
            name: "default_name_5"
            remote-gw: "<your_own_value>"




