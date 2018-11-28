==========================
fortios_system_auto_script
==========================


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
      - name: Configure auto script.
        fortios_system_auto_script:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_auto_script:
            state: "present"
            interval: "3"
            name: "default_name_4"
            output-size: "5"
            repeat: "6"
            script: "<your_own_value>"
            start: "manual"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_auto_script_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure auto script.
        fortios_system_auto_script:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_auto_script:
            state: "present"
            interval: "3"
            name: "default_name_4"
            output-size: "5"
            repeat: "6"
            script: "<your_own_value>"
            start: "manual"




