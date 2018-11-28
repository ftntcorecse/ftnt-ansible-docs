=========================
fortios_system_sms_server
=========================


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
      - name: Configure SMS server for sending SMS messages to support user authentication.
        fortios_system_sms_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_sms_server:
            state: "present"
            mail-server: "<your_own_value>"
            name: "default_name_4"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_sms_server_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure SMS server for sending SMS messages to support user authentication.
        fortios_system_sms_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_sms_server:
            state: "present"
            mail-server: "<your_own_value>"
            name: "default_name_4"




