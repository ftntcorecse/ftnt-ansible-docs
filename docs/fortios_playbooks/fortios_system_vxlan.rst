====================
fortios_system_vxlan
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
      - name: Configure VXLAN devices.
        fortios_system_vxlan:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vxlan:
            state: "present"
            dstport: "3"
            interface: "<your_own_value> (source system.interface.name)"
            ip-version: "ipv4-unicast"
            multicast-ttl: "6"
            name: "default_name_7"
            remote-ip:
             -
                ip: "<your_own_value>"
            remote-ip6:
             -
                ip6: "<your_own_value>"
            vni: "12"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vxlan_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure VXLAN devices.
        fortios_system_vxlan:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vxlan:
            state: "present"
            dstport: "3"
            interface: "<your_own_value> (source system.interface.name)"
            ip-version: "ipv4-unicast"
            multicast-ttl: "6"
            name: "default_name_7"
            remote-ip:
             -
                ip: "<your_own_value>"
            remote-ip6:
             -
                ip6: "<your_own_value>"
            vni: "12"




