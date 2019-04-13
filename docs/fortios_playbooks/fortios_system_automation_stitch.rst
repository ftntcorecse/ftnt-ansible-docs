================================
fortios_system_automation_stitch
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
      - name: Automation stitches.
        fortios_system_automation_stitch:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_stitch:
            state: "present"
            action:
             -
                name: "default_name_4 (source system.automation-action.name)"
            destination:
             -
                name: "default_name_6 (source system.automation-destination.name)"
            name: "default_name_7"
            status: "enable"
            trigger: "<your_own_value> (source system.automation-trigger.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_automation_stitch_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Automation stitches.
        fortios_system_automation_stitch:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_stitch:
            state: "present"
            action:
             -
                name: "default_name_4 (source system.automation-action.name)"
            destination:
             -
                name: "default_name_6 (source system.automation-destination.name)"
            name: "default_name_7"
            status: "enable"
            trigger: "<your_own_value> (source system.automation-trigger.name)"




