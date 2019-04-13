========================
fortios_router_key_chain
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
      - name: Configure key-chain.
        fortios_router_key_chain:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_key_chain:
            state: "present"
            key:
             -
                accept-lifetime: "<your_own_value>"
                id:  "5"
                key-string: "<your_own_value>"
                send-lifetime: "<your_own_value>"
            name: "default_name_8"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/router/fortios_router_key_chain_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure key-chain.
        fortios_router_key_chain:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_key_chain:
            state: "present"
            key:
             -
                accept-lifetime: "<your_own_value>"
                id:  "5"
                key-string: "<your_own_value>"
                send-lifetime: "<your_own_value>"
            name: "default_name_8"




