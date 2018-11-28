====================================
fortios_switch_controller_quarantine
====================================


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
      - name: Configure FortiSwitch quarantine support.
        fortios_switch_controller_quarantine:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_quarantine:
            quarantine: "enable"
            targets:
             -
                description: "<your_own_value>"
                entry-id: "6"
                mac: "<your_own_value>"
                tag:
                 -
                    tags: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_quarantine_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch quarantine support.
        fortios_switch_controller_quarantine:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_quarantine:
            quarantine: "enable"
            targets:
             -
                description: "<your_own_value>"
                entry-id: "6"
                mac: "<your_own_value>"
                tag:
                 -
                    tags: "<your_own_value>"




