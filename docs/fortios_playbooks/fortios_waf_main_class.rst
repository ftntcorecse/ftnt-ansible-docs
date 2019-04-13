======================
fortios_waf_main_class
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
      - name: Hidden table for datasource.
        fortios_waf_main_class:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          waf_main_class:
            state: "present"
            id:  "3"
            name: "default_name_4"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/waf/fortios_waf_main_class_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Hidden table for datasource.
        fortios_waf_main_class:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          waf_main_class:
            state: "present"
            id:  "3"
            name: "default_name_4"




