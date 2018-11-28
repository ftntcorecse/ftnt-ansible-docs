==================================================
fortios_switch_controller_network_monitor_settings
==================================================


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
      - name: Configure network monitor settings.
        fortios_switch_controller_network_monitor_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_network_monitor_settings:
            network-monitoring: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_network_monitor_settings_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure network monitor settings.
        fortios_switch_controller_network_monitor_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_network_monitor_settings:
            network-monitoring: "enable"




