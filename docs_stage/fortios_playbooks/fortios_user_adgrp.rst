==================
fortios_user_adgrp
==================


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
      - name: Configure FSSO groups.
        fortios_user_adgrp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_adgrp:
            state: "present"
            name: "default_name_3"
            server-name: "<your_own_value> (source user.fsso.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_adgrp_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FSSO groups.
        fortios_user_adgrp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_adgrp:
            state: "present"
            name: "default_name_3"
            server-name: "<your_own_value> (source user.fsso.name)"




