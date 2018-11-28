===============================
fortios_system_switch_interface
===============================


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
      - name: Configure software switch interfaces by grouping physical and WiFi interfaces.
        fortios_system_switch_interface:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_switch_interface:
            state: "present"
            intra-switch-policy: "implicit"
            member:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            name: "default_name_6"
            span: "disable"
            span-dest-port: "<your_own_value> (source system.interface.name)"
            span-direction: "rx"
            span-source-port:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            type: "switch"
            vdom: "<your_own_value> (source system.vdom.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_switch_interface_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure software switch interfaces by grouping physical and WiFi interfaces.
        fortios_system_switch_interface:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_switch_interface:
            state: "present"
            intra-switch-policy: "implicit"
            member:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            name: "default_name_6"
            span: "disable"
            span-dest-port: "<your_own_value> (source system.interface.name)"
            span-direction: "rx"
            span-source-port:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            type: "switch"
            vdom: "<your_own_value> (source system.vdom.name)"




