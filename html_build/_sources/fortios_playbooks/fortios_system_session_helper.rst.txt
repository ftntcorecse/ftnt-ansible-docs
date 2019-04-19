=============================
fortios_system_session_helper
=============================


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
      - name: Configure session helper.
        fortios_system_session_helper:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_session_helper:
            state: "present"
            id:  "3"
            name: "default_name_4"
            port: "5"
            protocol: "6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_session_helper_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure session helper.
        fortios_system_session_helper:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_session_helper:
            state: "present"
            id:  "3"
            name: "default_name_4"
            port: "5"
            protocol: "6"




