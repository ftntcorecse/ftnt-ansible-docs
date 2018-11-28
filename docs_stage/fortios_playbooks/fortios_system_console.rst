======================
fortios_system_console
======================


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
      - name: Configure console.
        fortios_system_console:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_console:
            baudrate: "9600"
            login: "enable"
            mode: "batch"
            output: "standard"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_console_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure console.
        fortios_system_console:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_console:
            baudrate: "9600"
            login: "enable"
            mode: "batch"
            output: "standard"




