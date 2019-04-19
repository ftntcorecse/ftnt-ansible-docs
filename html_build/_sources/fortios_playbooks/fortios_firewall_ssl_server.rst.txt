===========================
fortios_firewall_ssl_server
===========================


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
      - name: Configure SSL servers.
        fortios_firewall_ssl_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ssl_server:
            state: "present"
            add-header-x-forwarded-proto: "enable"
            ip: "<your_own_value>"
            mapped-port: "5"
            name: "default_name_6"
            port: "7"
            ssl-algorithm: "high"
            ssl-cert: "<your_own_value> (source vpn.certificate.local.name)"
            ssl-client-renegotiation: "allow"
            ssl-dh-bits: "768"
            ssl-max-version: "tls-1.0"
            ssl-min-version: "tls-1.0"
            ssl-mode: "half"
            ssl-send-empty-frags: "enable"
            url-rewrite: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_ssl_server_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure SSL servers.
        fortios_firewall_ssl_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ssl_server:
            state: "present"
            add-header-x-forwarded-proto: "enable"
            ip: "<your_own_value>"
            mapped-port: "5"
            name: "default_name_6"
            port: "7"
            ssl-algorithm: "high"
            ssl-cert: "<your_own_value> (source vpn.certificate.local.name)"
            ssl-client-renegotiation: "allow"
            ssl-dh-bits: "768"
            ssl-max-version: "tls-1.0"
            ssl-min-version: "tls-1.0"
            ssl-mode: "half"
            ssl-send-empty-frags: "enable"
            url-rewrite: "enable"




