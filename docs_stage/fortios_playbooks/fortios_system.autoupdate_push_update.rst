=====================================
fortios_system.autoupdate_push_update
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
      - name: Configure push updates.
        fortios_system.autoupdate_push_update:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.autoupdate_push_update:
            address: "<your_own_value>"
            override: "enable"
            port: "5"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system.autoupdate/fortios_system.autoupdate_push_update_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure push updates.
        fortios_system.autoupdate_push_update:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.autoupdate_push_update:
            address: "<your_own_value>"
            override: "enable"
            port: "5"
            status: "enable"




