===============================
fortios_firewall.schedule_group
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
      - name: Schedule group configuration.
        fortios_firewall.schedule_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.schedule_group:
            state: "present"
            color: "3"
            member:
             -
                name: "default_name_5 (source firewall.schedule.onetime.name firewall.schedule.recurring.name)"
            name: "default_name_6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.schedule/fortios_firewall.schedule_group_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Schedule group configuration.
        fortios_firewall.schedule_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.schedule_group:
            state: "present"
            color: "3"
            member:
             -
                name: "default_name_5 (source firewall.schedule.onetime.name firewall.schedule.recurring.name)"
            name: "default_name_6"




