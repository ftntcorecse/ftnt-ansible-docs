==============================
fortios_system_resource_limits
==============================


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
      - name: Configure resource limits.
        fortios_system_resource_limits:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_resource_limits:
            custom-service: "3"
            dialup-tunnel: "4"
            firewall-address: "5"
            firewall-addrgrp: "6"
            firewall-policy: "7"
            ipsec-phase1: "8"
            ipsec-phase1-interface: "9"
            ipsec-phase2: "10"
            ipsec-phase2-interface: "11"
            log-disk-quota: "12"
            onetime-schedule: "13"
            proxy: "14"
            recurring-schedule: "15"
            service-group: "16"
            session: "17"
            sslvpn: "18"
            user: "19"
            user-group: "20"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_resource_limits_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure resource limits.
        fortios_system_resource_limits:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_resource_limits:
            custom-service: "3"
            dialup-tunnel: "4"
            firewall-address: "5"
            firewall-addrgrp: "6"
            firewall-policy: "7"
            ipsec-phase1: "8"
            ipsec-phase1-interface: "9"
            ipsec-phase2: "10"
            ipsec-phase2-interface: "11"
            log-disk-quota: "12"
            onetime-schedule: "13"
            proxy: "14"
            recurring-schedule: "15"
            service-group: "16"
            session: "17"
            sslvpn: "18"
            user: "19"
            user-group: "20"




