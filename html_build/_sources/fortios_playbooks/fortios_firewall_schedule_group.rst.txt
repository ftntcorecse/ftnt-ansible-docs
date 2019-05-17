===============================
fortios_firewall_schedule_group
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
        fortios_firewall_schedule_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          firewall_schedule_group:
            state: "present"
            color: "3"
            member:
             -
                name: "default_name_5 (source firewall.schedule.onetime.name firewall.schedule.recurring.name)"
            name: "default_name_6"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

