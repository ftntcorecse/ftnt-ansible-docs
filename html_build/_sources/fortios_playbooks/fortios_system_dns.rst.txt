==================
fortios_system_dns
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
      - name: Configure DNS.
        fortios_system_dns:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dns:
            cache-notfound-responses: "disable"
            dns-cache-limit: "4"
            dns-cache-ttl: "5"
            domain: "<your_own_value>"
            ip6-primary: "<your_own_value>"
            ip6-secondary: "<your_own_value>"
            primary: "<your_own_value>"
            secondary: "<your_own_value>"
            source-ip: "84.230.14.43"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_dns_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure DNS.
        fortios_system_dns:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dns:
            cache-notfound-responses: "disable"
            dns-cache-limit: "4"
            dns-cache-ttl: "5"
            domain: "<your_own_value>"
            ip6-primary: "<your_own_value>"
            ip6-secondary: "<your_own_value>"
            primary: "<your_own_value>"
            secondary: "<your_own_value>"
            source-ip: "84.230.14.43"




