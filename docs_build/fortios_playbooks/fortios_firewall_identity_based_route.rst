=====================================
fortios_firewall_identity_based_route
=====================================


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
      - name: Configure identity based routing.
        fortios_firewall_identity_based_route:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_identity_based_route:
            state: "present"
            comments: "<your_own_value>"
            name: "default_name_4"
            rule:
             -
                device: "<your_own_value> (source system.interface.name)"
                gateway: "<your_own_value>"
                groups:
                 -
                    name: "default_name_9 (source user.group.name)"
                id:  "10"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_identity_based_route_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure identity based routing.
        fortios_firewall_identity_based_route:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_identity_based_route:
            state: "present"
            comments: "<your_own_value>"
            name: "default_name_4"
            rule:
             -
                device: "<your_own_value> (source system.interface.name)"
                gateway: "<your_own_value>"
                groups:
                 -
                    name: "default_name_9 (source user.group.name)"
                id:  "10"




