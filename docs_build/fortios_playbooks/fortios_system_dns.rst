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
          https: "False"
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

%%PB_FILE_EXAMPLE_TOKEN%%

