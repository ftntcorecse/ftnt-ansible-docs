================
fortios_ips_rule
================


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
      - name: Configure IPS rules.
        fortios_ips_rule:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_rule:
            state: "present"
            action: "pass"
            application: "<your_own_value>"
            date: "5"
            group: "<your_own_value>"
            location: "<your_own_value>"
            log: "disable"
            log-packet: "disable"
            metadata:
             -
                id:  "11"
                metaid: "12"
                valueid: "13"
            name: "default_name_14"
            os: "<your_own_value>"
            rev: "16"
            rule-id: "17"
            service: "<your_own_value>"
            severity: "<your_own_value>"
            status: "disable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/ips/fortios_ips_rule_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS rules.
        fortios_ips_rule:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_rule:
            state: "present"
            action: "pass"
            application: "<your_own_value>"
            date: "5"
            group: "<your_own_value>"
            location: "<your_own_value>"
            log: "disable"
            log-packet: "disable"
            metadata:
             -
                id:  "11"
                metaid: "12"
                valueid: "13"
            name: "default_name_14"
            os: "<your_own_value>"
            rev: "16"
            rule-id: "17"
            service: "<your_own_value>"
            severity: "<your_own_value>"
            status: "disable"




