===========================
fortios_system_fortisandbox
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
      - name: Configure FortiSandbox.
        fortios_system_fortisandbox:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fortisandbox:
            email: "<your_own_value>"
            enc-algorithm: "default"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            ssl-min-proto-version: "default"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_fortisandbox_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSandbox.
        fortios_system_fortisandbox:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fortisandbox:
            email: "<your_own_value>"
            enc-algorithm: "default"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            ssl-min-proto-version: "default"
            status: "enable"




