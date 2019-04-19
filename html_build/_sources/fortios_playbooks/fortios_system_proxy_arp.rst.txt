========================
fortios_system_proxy_arp
========================


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
      - name: Configure proxy-ARP.
        fortios_system_proxy_arp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_proxy_arp:
            state: "present"
            end-ip: "<your_own_value>"
            id:  "4"
            interface: "<your_own_value> (source system.interface.name)"
            ip: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_proxy_arp_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure proxy-ARP.
        fortios_system_proxy_arp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_proxy_arp:
            state: "present"
            end-ip: "<your_own_value>"
            id:  "4"
            interface: "<your_own_value> (source system.interface.name)"
            ip: "<your_own_value>"




