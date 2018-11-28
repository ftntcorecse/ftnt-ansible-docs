==================================
fortios_system.autoupdate_schedule
==================================


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
      - name: Configure update schedule.
        fortios_system.autoupdate_schedule:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.autoupdate_schedule:
            day: "Sunday"
            frequency: "every"
            status: "enable"
            time: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system.autoupdate/fortios_system.autoupdate_schedule_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure update schedule.
        fortios_system.autoupdate_schedule:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.autoupdate_schedule:
            day: "Sunday"
            frequency: "every"
            status: "enable"
            time: "<your_own_value>"




