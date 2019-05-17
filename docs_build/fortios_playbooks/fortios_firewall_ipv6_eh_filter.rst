===============================
fortios_firewall_ipv6_eh_filter
===============================


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
      - name: Configure IPv6 extension header filter.
        fortios_firewall_ipv6_eh_filter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ipv6_eh_filter:
            auth: "enable"
            dest-opt: "enable"
            fragment: "enable"
            hdopt-type: "6"
            hop-opt: "enable"
            no-next: "enable"
            routing: "enable"
            routing-type: "10"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

