========================================
fortios_switch_controller_custom_command
========================================


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
      - name: Configure the FortiGate switch controller to send custom commands to managed FortiSwitch devices.
        fortios_switch_controller_custom_command:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_custom_command:
            state: "present"
            command: "<your_own_value>"
            command-name: "<your_own_value>"
            description: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_custom_command_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure the FortiGate switch controller to send custom commands to managed FortiSwitch devices.
        fortios_switch_controller_custom_command:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_custom_command:
            state: "present"
            command: "<your_own_value>"
            command-name: "<your_own_value>"
            description: "<your_own_value>"




