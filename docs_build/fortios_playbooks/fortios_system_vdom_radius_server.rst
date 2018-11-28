=================================
fortios_system_vdom_radius_server
=================================


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
      - name: Configure a RADIUS server to use as a RADIUS Single Sign On (RSSO) server for this VDOM.
        fortios_system_vdom_radius_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_radius_server:
            state: "present"
            name: "default_name_3 (source system.vdom.name)"
            radius-server-vdom: "<your_own_value> (source system.vdom.name)"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vdom_radius_server_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure a RADIUS server to use as a RADIUS Single Sign On (RSSO) server for this VDOM.
        fortios_system_vdom_radius_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_radius_server:
            state: "present"
            name: "default_name_3 (source system.vdom.name)"
            radius-server-vdom: "<your_own_value> (source system.vdom.name)"
            status: "enable"




