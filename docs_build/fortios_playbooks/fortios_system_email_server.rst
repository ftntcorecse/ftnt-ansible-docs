===========================
fortios_system_email_server
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
      - name: Configure the email server used by the FortiGate various things. For example, for sending email messages to users to support user authentication
         features.
        fortios_system_email_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_email_server:
            authenticate: "enable"
            password: "<your_own_value>"
            port: "5"
            reply-to: "<your_own_value>"
            security: "none"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            source-ip6: "<your_own_value>"
            ssl-min-proto-version: "default"
            type: "custom"
            username: "<your_own_value>"
            validate-server: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_email_server_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure the email server used by the FortiGate various things. For example, for sending email messages to users to support user authentication features.
        fortios_system_email_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_email_server:
            authenticate: "enable"
            password: "<your_own_value>"
            port: "5"
            reply-to: "<your_own_value>"
            security: "none"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            source-ip6: "<your_own_value>"
            ssl-min-proto-version: "default"
            type: "custom"
            username: "<your_own_value>"
            validate-server: "enable"




