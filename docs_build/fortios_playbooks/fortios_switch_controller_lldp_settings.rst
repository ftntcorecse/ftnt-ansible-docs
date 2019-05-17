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
          https: "False"
          switch_controller_lldp_settings:
            fast-start-interval: "3"
            management-interface: "internal"
            status: "enable"
            tx-hold: "6"
            tx-interval: "7"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

