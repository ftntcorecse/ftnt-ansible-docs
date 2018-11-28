=================================
fortios_system_automation_trigger
=================================


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
      - name: Trigger for automation stitches.
        fortios_system_automation_trigger:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_trigger:
            state: "present"
            event-type: "ioc"
            ioc-level: "medium"
            license-type: "forticare-support"
            logid: "6"
            name: "default_name_7"
            trigger-day: "8"
            trigger-frequency: "hourly"
            trigger-hour: "10"
            trigger-minute: "11"
            trigger-type: "event-based"
            trigger-weekday: "sunday"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_automation_trigger_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Trigger for automation stitches.
        fortios_system_automation_trigger:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_trigger:
            state: "present"
            event-type: "ioc"
            ioc-level: "medium"
            license-type: "forticare-support"
            logid: "6"
            name: "default_name_7"
            trigger-day: "8"
            trigger-frequency: "hourly"
            trigger-hour: "10"
            trigger-minute: "11"
            trigger-type: "event-based"
            trigger-weekday: "sunday"




