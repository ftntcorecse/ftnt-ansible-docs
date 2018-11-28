======================
fortios_router_setting
======================


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
      - name: Configure router settings.
        fortios_router_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_setting:
            hostname: "myhostname"
            show-filter: "<your_own_value> (source router.prefix-list.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/router/fortios_router_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure router settings.
        fortios_router_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_setting:
            hostname: "myhostname"
            show-filter: "<your_own_value> (source router.prefix-list.name)"




