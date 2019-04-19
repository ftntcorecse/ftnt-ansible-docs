=======================
fortios_user_quarantine
=======================


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
      - name: Configure quarantine support.
        fortios_user_quarantine:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_quarantine:
            quarantine: "enable"
            targets:
             -
                description: "<your_own_value>"
                entry: "<your_own_value>"
                macs:
                 -
                    description: "<your_own_value>"
                    entry-id: "9"
                    mac: "<your_own_value>"
                    parent: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_quarantine_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure quarantine support.
        fortios_user_quarantine:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_quarantine:
            quarantine: "enable"
            targets:
             -
                description: "<your_own_value>"
                entry: "<your_own_value>"
                macs:
                 -
                    description: "<your_own_value>"
                    entry-id: "9"
                    mac: "<your_own_value>"
                    parent: "<your_own_value>"




