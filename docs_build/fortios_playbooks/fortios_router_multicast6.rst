=========================
fortios_router_multicast6
=========================


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
      - name: Configure IPv6 multicast.
        fortios_router_multicast6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          router_multicast6:
            interface:
             -
                hello-holdtime: "4"
                hello-interval: "5"
                name: "default_name_6 (source system.interface.name)"
            multicast-pmtu: "enable"
            multicast-routing: "enable"
            pim-sm-global:
                register-rate-limit: "10"
                rp-address:
                 -
                    id:  "12"
                    ip6-address: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

