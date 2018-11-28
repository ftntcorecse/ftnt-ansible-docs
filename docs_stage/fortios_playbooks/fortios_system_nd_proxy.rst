=======================
fortios_system_nd_proxy
=======================


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
      - name: Configure IPv6 neighbor discovery proxy (RFC4389).
        fortios_system_nd_proxy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_nd_proxy:
            member:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_nd_proxy_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPv6 neighbor discovery proxy (RFC4389).
        fortios_system_nd_proxy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_nd_proxy:
            member:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            status: "enable"




