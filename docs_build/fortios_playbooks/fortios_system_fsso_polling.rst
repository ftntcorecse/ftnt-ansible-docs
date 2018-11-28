===========================
fortios_system_fsso_polling
===========================


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
      - name: Configure Fortinet Single Sign On (FSSO) server.
        fortios_system_fsso_polling:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fsso_polling:
            auth-password: "<your_own_value>"
            authentication: "enable"
            listening-port: "5"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_fsso_polling_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure Fortinet Single Sign On (FSSO) server.
        fortios_system_fsso_polling:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fsso_polling:
            auth-password: "<your_own_value>"
            authentication: "enable"
            listening-port: "5"
            status: "enable"




