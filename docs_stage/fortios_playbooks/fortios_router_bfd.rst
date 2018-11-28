==================
fortios_router_bfd
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
      - name: Configure BFD.
        fortios_router_bfd:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_bfd:
            neighbor:
             -
                interface: "<your_own_value> (source system.interface.name)"
                ip: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/router/fortios_router_bfd_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure BFD.
        fortios_router_bfd:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_bfd:
            neighbor:
             -
                interface: "<your_own_value> (source system.interface.name)"
                ip: "<your_own_value>"




