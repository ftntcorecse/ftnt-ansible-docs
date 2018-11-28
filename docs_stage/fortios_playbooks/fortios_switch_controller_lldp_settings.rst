=======================================
fortios_switch_controller_lldp_settings
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
      - name: Configure FortiSwitch LLDP settings.
        fortios_switch_controller_lldp_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_lldp_settings:
            fast-start-interval: "3"
            management-interface: "internal"
            status: "enable"
            tx-hold: "6"
            tx-interval: "7"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_lldp_settings_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch LLDP settings.
        fortios_switch_controller_lldp_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_lldp_settings:
            fast-start-interval: "3"
            management-interface: "internal"
            status: "enable"
            tx-hold: "6"
            tx-interval: "7"




