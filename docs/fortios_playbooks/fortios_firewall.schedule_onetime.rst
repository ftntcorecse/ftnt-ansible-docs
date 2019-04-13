=================================
fortios_firewall.schedule_onetime
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
      - name: Onetime schedule configuration.
        fortios_firewall.schedule_onetime:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.schedule_onetime:
            state: "present"
            color: "3"
            end: "<your_own_value>"
            expiration-days: "5"
            name: "default_name_6"
            start: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.schedule/fortios_firewall.schedule_onetime_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Onetime schedule configuration.
        fortios_firewall.schedule_onetime:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.schedule_onetime:
            state: "present"
            color: "3"
            end: "<your_own_value>"
            expiration-days: "5"
            name: "default_name_6"
            start: "<your_own_value>"




