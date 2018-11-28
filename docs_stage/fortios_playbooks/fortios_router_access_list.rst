==========================
fortios_router_access_list
==========================


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
      - name: Configure access lists.
        fortios_router_access_list:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_access_list:
            state: "present"
            comments: "<your_own_value>"
            name: "default_name_4"
            rule:
             -
                action: "permit"
                exact-match: "enable"
                flags: "8"
                id:  "9"
                prefix: "<your_own_value>"
                wildcard: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/router/fortios_router_access_list_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure access lists.
        fortios_router_access_list:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_access_list:
            state: "present"
            comments: "<your_own_value>"
            name: "default_name_4"
            rule:
             -
                action: "permit"
                exact-match: "enable"
                flags: "8"
                id:  "9"
                prefix: "<your_own_value>"
                wildcard: "<your_own_value>"




