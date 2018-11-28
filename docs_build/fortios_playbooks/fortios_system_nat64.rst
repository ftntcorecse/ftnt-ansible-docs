====================
fortios_system_nat64
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
      - name: Configure NAT64.
        fortios_system_nat64:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_nat64:
            always-synthesize-aaaa-record: "enable"
            generate-ipv6-fragment-header: "enable"
            nat64-prefix: "<your_own_value>"
            secondary-prefix:
             -
                name: "default_name_7"
                nat64-prefix: "<your_own_value>"
            secondary-prefix-status: "enable"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_nat64_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure NAT64.
        fortios_system_nat64:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_nat64:
            always-synthesize-aaaa-record: "enable"
            generate-ipv6-fragment-header: "enable"
            nat64-prefix: "<your_own_value>"
            secondary-prefix:
             -
                name: "default_name_7"
                nat64-prefix: "<your_own_value>"
            secondary-prefix-status: "enable"
            status: "enable"




