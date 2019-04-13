======================================
fortios_switch_controller_switch_group
======================================


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
      - name: Configure FortiSwitch switch groups.
        fortios_switch_controller_switch_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_switch_group:
            state: "present"
            description: "<your_own_value>"
            members:
             -
                name: "default_name_5 (source switch-controller.managed-switch.switch-id)"
            name: "default_name_6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_switch_group_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch switch groups.
        fortios_switch_controller_switch_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_switch_group:
            state: "present"
            description: "<your_own_value>"
            members:
             -
                name: "default_name_5 (source switch-controller.managed-switch.switch-id)"
            name: "default_name_6"




