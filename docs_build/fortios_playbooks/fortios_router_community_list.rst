=============================
fortios_router_community_list
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
      - name: Configure community lists.
        fortios_router_community_list:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_community_list:
            state: "present"
            name: "default_name_3"
            rule:
             -
                action: "deny"
                id:  "6"
                match: "<your_own_value>"
                regexp: "<your_own_value>"
            type: "standard"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/router/fortios_router_community_list_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure community lists.
        fortios_router_community_list:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_community_list:
            state: "present"
            name: "default_name_3"
            rule:
             -
                action: "deny"
                id:  "6"
                match: "<your_own_value>"
                regexp: "<your_own_value>"
            type: "standard"




