====================
fortios_system_sflow
====================


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
      - name: Configure sFlow.
        fortios_system_sflow:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_sflow:
            collector-ip: "<your_own_value>"
            collector-port: "4"
            source-ip: "84.230.14.43"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_sflow_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure sFlow.
        fortios_system_sflow:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_sflow:
            collector-ip: "<your_own_value>"
            collector-port: "4"
            source-ip: "84.230.14.43"




