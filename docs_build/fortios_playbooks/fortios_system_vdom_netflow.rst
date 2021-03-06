===========================
fortios_system_vdom_netflow
===========================


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
      - name: Configure NetFlow per VDOM.
        fortios_system_vdom_netflow:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_netflow:
            collector-ip: "<your_own_value>"
            collector-port: "4"
            source-ip: "84.230.14.43"
            vdom-netflow: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vdom_netflow_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure NetFlow per VDOM.
        fortios_system_vdom_netflow:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_netflow:
            collector-ip: "<your_own_value>"
            collector-port: "4"
            source-ip: "84.230.14.43"
            vdom-netflow: "enable"




