====================
fortios_ips_settings
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
      - name: Configure IPS VDOM parameter.
        fortios_ips_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_settings:
            ips-packet-quota: "3"
            packet-log-history: "4"
            packet-log-memory: "5"
            packet-log-post-attack: "6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/ips/fortios_ips_settings_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS VDOM parameter.
        fortios_ips_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_settings:
            ips-packet-quota: "3"
            packet-log-history: "4"
            packet-log-memory: "5"
            packet-log-post-attack: "6"




