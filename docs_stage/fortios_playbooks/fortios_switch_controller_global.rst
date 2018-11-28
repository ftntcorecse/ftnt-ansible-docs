================================
fortios_switch_controller_global
================================


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
      - name: Configure FortiSwitch global settings.
        fortios_switch_controller_global:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_global:
            allow-multiple-interfaces: "enable"
            default-virtual-switch-vlan: "<your_own_value> (source system.interface.name)"
            disable-discovery:
             -
                name: "default_name_6"
            https-image-push: "enable"
            log-mac-limit-violations: "enable"
            mac-aging-interval: "9"
            mac-retention-period: "10"
            mac-violation-timer: "11"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_global_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch global settings.
        fortios_switch_controller_global:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_global:
            allow-multiple-interfaces: "enable"
            default-virtual-switch-vlan: "<your_own_value> (source system.interface.name)"
            disable-discovery:
             -
                name: "default_name_6"
            https-image-push: "enable"
            log-mac-limit-violations: "enable"
            mac-aging-interval: "9"
            mac-retention-period: "10"
            mac-violation-timer: "11"




