===================
fortios_log_setting
===================


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
      - name: Configure general log settings.
        fortios_log_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log_setting:
            brief-traffic-format: "enable"
            custom-log-fields:
             -
                field-id: "<your_own_value> (source log.custom-field.id)"
            daemon-log: "enable"
            expolicy-implicit-log: "enable"
            fwpolicy-implicit-log: "enable"
            fwpolicy6-implicit-log: "enable"
            local-in-allow: "enable"
            local-in-deny-broadcast: "enable"
            local-in-deny-unicast: "enable"
            local-out: "enable"
            log-invalid-packet: "enable"
            log-policy-comment: "enable"
            log-policy-name: "enable"
            log-user-in-upper: "enable"
            neighbor-event: "enable"
            resolve-ip: "enable"
            resolve-port: "enable"
            user-anonymize: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log/fortios_log_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure general log settings.
        fortios_log_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log_setting:
            brief-traffic-format: "enable"
            custom-log-fields:
             -
                field-id: "<your_own_value> (source log.custom-field.id)"
            daemon-log: "enable"
            expolicy-implicit-log: "enable"
            fwpolicy-implicit-log: "enable"
            fwpolicy6-implicit-log: "enable"
            local-in-allow: "enable"
            local-in-deny-broadcast: "enable"
            local-in-deny-unicast: "enable"
            local-out: "enable"
            log-invalid-packet: "enable"
            log-policy-comment: "enable"
            log-policy-name: "enable"
            log-user-in-upper: "enable"
            neighbor-event: "enable"
            resolve-ip: "enable"
            resolve-port: "enable"
            user-anonymize: "enable"




