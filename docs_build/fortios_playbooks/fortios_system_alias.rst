====================
fortios_system_alias
====================


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
      - name: Configure alias command.
        fortios_system_alias:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_alias:
            state: "present"
            command: "<your_own_value>"
            name: "default_name_4"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_alias_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure alias command.
        fortios_system_alias:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_alias:
            state: "present"
            command: "<your_own_value>"
            name: "default_name_4"




