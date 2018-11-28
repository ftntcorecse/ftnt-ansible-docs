==========================================================
fortios_wireless_controller.hotspot20_h2qp_conn_capability
==========================================================


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
      - name: Configure connection capability.
        fortios_wireless_controller.hotspot20_h2qp_conn_capability:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_h2qp_conn_capability:
            state: "present"
            esp-port: "closed"
            ftp-port: "closed"
            http-port: "closed"
            icmp-port: "closed"
            ikev2-port: "closed"
            ikev2-xx-port: "closed"
            name: "default_name_9"
            pptp-vpn-port: "closed"
            ssh-port: "closed"
            tls-port: "closed"
            voip-tcp-port: "closed"
            voip-udp-port: "closed"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_h2qp_conn_capability_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure connection capability.
        fortios_wireless_controller.hotspot20_h2qp_conn_capability:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_h2qp_conn_capability:
            state: "present"
            esp-port: "closed"
            ftp-port: "closed"
            http-port: "closed"
            icmp-port: "closed"
            ikev2-port: "closed"
            ikev2-xx-port: "closed"
            name: "default_name_9"
            pptp-vpn-port: "closed"
            ssh-port: "closed"
            tls-port: "closed"
            voip-tcp-port: "closed"
            voip-udp-port: "closed"




