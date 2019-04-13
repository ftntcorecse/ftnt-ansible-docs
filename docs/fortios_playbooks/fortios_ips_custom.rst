==================
fortios_ips_custom
==================


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
      - name: Configure IPS custom signature.
        fortios_ips_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_custom:
            state: "present"
            action: "pass"
            application: "<your_own_value>"
            comment: "Comment."
            location: "<your_own_value>"
            log: "disable"
            log-packet: "disable"
            os: "<your_own_value>"
            protocol: "<your_own_value>"
            rule-id: "11"
            severity: "<your_own_value>"
            sig-name: "<your_own_value>"
            signature: "<your_own_value>"
            status: "disable"
            tag: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/ips/fortios_ips_custom_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS custom signature.
        fortios_ips_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_custom:
            state: "present"
            action: "pass"
            application: "<your_own_value>"
            comment: "Comment."
            location: "<your_own_value>"
            log: "disable"
            log-packet: "disable"
            os: "<your_own_value>"
            protocol: "<your_own_value>"
            rule-id: "11"
            severity: "<your_own_value>"
            sig-name: "<your_own_value>"
            signature: "<your_own_value>"
            status: "disable"
            tag: "<your_own_value>"




