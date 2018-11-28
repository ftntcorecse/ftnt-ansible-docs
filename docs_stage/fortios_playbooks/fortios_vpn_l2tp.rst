================
fortios_vpn_l2tp
================


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
      - name: Configure L2TP.
        fortios_vpn_l2tp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn_l2tp:
            eip: "<your_own_value>"
            enforce-ipsec: "enable"
            sip: "<your_own_value>"
            status: "enable"
            usrgrp: "<your_own_value> (source user.group.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn/fortios_vpn_l2tp_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure L2TP.
        fortios_vpn_l2tp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn_l2tp:
            eip: "<your_own_value>"
            enforce-ipsec: "enable"
            sip: "<your_own_value>"
            status: "enable"
            usrgrp: "<your_own_value> (source user.group.name)"




