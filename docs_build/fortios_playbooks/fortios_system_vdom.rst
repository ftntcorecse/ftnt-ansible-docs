===================
fortios_system_vdom
===================


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
      - name: Configure virtual domain.
        fortios_system_vdom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom:
            state: "present"
            name: "default_name_3"
            short-name: "<your_own_value>"
            temporary: "5"
            vcluster-id: "6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vdom_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure virtual domain.
        fortios_system_vdom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom:
            state: "present"
            name: "default_name_3"
            short-name: "<your_own_value>"
            temporary: "5"
            vcluster-id: "6"




