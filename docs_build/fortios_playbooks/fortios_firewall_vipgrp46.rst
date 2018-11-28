=========================
fortios_firewall_vipgrp46
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
      - name: Configure IPv4 to IPv6 virtual IP groups.
        fortios_firewall_vipgrp46:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_vipgrp46:
            state: "present"
            color: "3"
            comments: "<your_own_value>"
            member:
             -
                name: "default_name_6 (source firewall.vip46.name)"
            name: "default_name_7"
            uuid: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_vipgrp46_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPv4 to IPv6 virtual IP groups.
        fortios_firewall_vipgrp46:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_vipgrp46:
            state: "present"
            color: "3"
            comments: "<your_own_value>"
            member:
             -
                name: "default_name_6 (source firewall.vip46.name)"
            name: "default_name_7"
            uuid: "<your_own_value>"




