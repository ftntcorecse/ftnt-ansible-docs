====================
fortios_user_setting
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
      - name: Configure user authentication setting.
        fortios_user_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_setting:
            auth-blackout-time: "3"
            auth-ca-cert: "<your_own_value> (source vpn.certificate.local.name)"
            auth-cert: "<your_own_value> (source vpn.certificate.local.name)"
            auth-http-basic: "enable"
            auth-invalid-max: "7"
            auth-lockout-duration: "8"
            auth-lockout-threshold: "9"
            auth-portal-timeout: "10"
            auth-ports:
             -
                id:  "12"
                port: "13"
                type: "http"
            auth-secure-http: "enable"
            auth-src-mac: "enable"
            auth-ssl-allow-renegotiation: "enable"
            auth-timeout: "18"
            auth-timeout-type: "idle-timeout"
            auth-type: "http"
            radius-ses-timeout-act: "hard-timeout"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure user authentication setting.
        fortios_user_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_setting:
            auth-blackout-time: "3"
            auth-ca-cert: "<your_own_value> (source vpn.certificate.local.name)"
            auth-cert: "<your_own_value> (source vpn.certificate.local.name)"
            auth-http-basic: "enable"
            auth-invalid-max: "7"
            auth-lockout-duration: "8"
            auth-lockout-threshold: "9"
            auth-portal-timeout: "10"
            auth-ports:
             -
                id:  "12"
                port: "13"
                type: "http"
            auth-secure-http: "enable"
            auth-src-mac: "enable"
            auth-ssl-allow-renegotiation: "enable"
            auth-timeout: "18"
            auth-timeout-type: "idle-timeout"
            auth-type: "http"
            radius-ses-timeout-act: "hard-timeout"




