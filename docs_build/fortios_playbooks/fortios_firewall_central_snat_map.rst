=================================
fortios_firewall_central_snat_map
=================================


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
      - name: Configure central SNAT policies.
        fortios_firewall_central_snat_map:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_central_snat_map:
            state: "present"
            comments: "<your_own_value>"
            dst-addr:
             -
                name: "default_name_5 (source firewall.address.name firewall.addrgrp.name)"
            dstintf:
             -
                name: "default_name_7 (source system.interface.name system.zone.name)"
            nat: "disable"
            nat-ippool:
             -
                name: "default_name_10 (source firewall.ippool.name)"
            nat-port: "<your_own_value>"
            orig-addr:
             -
                name: "default_name_13 (source firewall.address.name firewall.addrgrp.name)"
            orig-port: "<your_own_value>"
            policyid: "15"
            protocol: "16"
            srcintf:
             -
                name: "default_name_18 (source system.interface.name system.zone.name)"
            status: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

