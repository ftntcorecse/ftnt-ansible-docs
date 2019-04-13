=============================
fortios_router_multicast_flow
=============================


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
      - name: Configure multicast-flow.
        fortios_router_multicast_flow:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_multicast_flow:
            state: "present"
            comments: "<your_own_value>"
            flows:
             -
                group-addr: "<your_own_value>"
                id:  "6"
                source-addr: "<your_own_value>"
            name: "default_name_8"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/router/fortios_router_multicast_flow_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure multicast-flow.
        fortios_router_multicast_flow:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_multicast_flow:
            state: "present"
            comments: "<your_own_value>"
            flows:
             -
                group-addr: "<your_own_value>"
                id:  "6"
                source-addr: "<your_own_value>"
            name: "default_name_8"




