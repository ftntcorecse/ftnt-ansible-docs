===================================
fortios_firewall.ipmacbinding_table
===================================


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
      - name: Configure IP to MAC address pairs in the IP/MAC binding table.
        fortios_firewall.ipmacbinding_table:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ipmacbinding_table:
            state: "present"
            ip: "<your_own_value>"
            mac: "<your_own_value>"
            name: "default_name_5"
            seq-num: "6"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.ipmacbinding/fortios_firewall.ipmacbinding_table_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IP to MAC address pairs in the IP/MAC binding table.
        fortios_firewall.ipmacbinding_table:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ipmacbinding_table:
            state: "present"
            ip: "<your_own_value>"
            mac: "<your_own_value>"
            name: "default_name_5"
            seq-num: "6"
            status: "enable"




