================
fortios_vpn_pptp
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
      - name: Configure PPTP.
        fortios_vpn_pptp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn_pptp:
            eip: "<your_own_value>"
            ip-mode: "range"
            local-ip: "<your_own_value>"
            sip: "<your_own_value>"
            status: "enable"
            usrgrp: "<your_own_value> (source user.group.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn/fortios_vpn_pptp_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure PPTP.
        fortios_vpn_pptp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn_pptp:
            eip: "<your_own_value>"
            ip-mode: "range"
            local-ip: "<your_own_value>"
            sip: "<your_own_value>"
            status: "enable"
            usrgrp: "<your_own_value> (source user.group.name)"




