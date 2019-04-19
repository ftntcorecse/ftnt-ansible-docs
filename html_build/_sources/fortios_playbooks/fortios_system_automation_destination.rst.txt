=====================================
fortios_system_automation_destination
=====================================


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
      - name: Automation destinations.
        fortios_system_automation_destination:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_destination:
            state: "present"
            destination:
             -
                name: "default_name_4"
            ha-group-id: "5"
            name: "default_name_6"
            type: "fortigate"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_automation_destination_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Automation destinations.
        fortios_system_automation_destination:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_destination:
            state: "present"
            destination:
             -
                name: "default_name_4"
            ha-group-id: "5"
            name: "default_name_6"
            type: "fortigate"




