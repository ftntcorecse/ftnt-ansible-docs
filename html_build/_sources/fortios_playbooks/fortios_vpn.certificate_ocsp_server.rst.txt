===================================
fortios_vpn.certificate_ocsp_server
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
      - name: OCSP server configuration.
        fortios_vpn.certificate_ocsp_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.certificate_ocsp_server:
            state: "present"
            cert: "<your_own_value> (source vpn.certificate.remote.name vpn.certificate.ca.name)"
            name: "default_name_4"
            secondary-cert: "<your_own_value> (source vpn.certificate.remote.name vpn.certificate.ca.name)"
            secondary-url: "<your_own_value>"
            source-ip: "84.230.14.43"
            unavail-action: "revoke"
            url: "myurl.com"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.certificate/fortios_vpn.certificate_ocsp_server_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: OCSP server configuration.
        fortios_vpn.certificate_ocsp_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.certificate_ocsp_server:
            state: "present"
            cert: "<your_own_value> (source vpn.certificate.remote.name vpn.certificate.ca.name)"
            name: "default_name_4"
            secondary-cert: "<your_own_value> (source vpn.certificate.remote.name vpn.certificate.ca.name)"
            secondary-url: "<your_own_value>"
            source-ip: "84.230.14.43"
            unavail-action: "revoke"
            url: "myurl.com"




