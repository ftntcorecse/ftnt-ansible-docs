====================
fortios_user_peergrp
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
      - name: Configure peer groups.
        fortios_user_peergrp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_peergrp:
            state: "present"
            member:
             -
                name: "default_name_4 (source user.peer.name)"
            name: "default_name_5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_peergrp_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure peer groups.
        fortios_user_peergrp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_peergrp:
            state: "present"
            member:
             -
                name: "default_name_4 (source user.peer.name)"
            name: "default_name_5"




