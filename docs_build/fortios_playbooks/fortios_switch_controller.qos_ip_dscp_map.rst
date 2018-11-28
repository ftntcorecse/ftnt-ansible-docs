=========================================
fortios_switch_controller.qos_ip_dscp_map
=========================================


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
      - name: Configure FortiSwitch QoS IP precedence/DSCP.
        fortios_switch_controller.qos_ip_dscp_map:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller.qos_ip_dscp_map:
            state: "present"
            description: "<your_own_value>"
            map:
             -
                cos-queue: "5"
                diffserv: "CS0"
                ip-precedence: "network-control"
                name: "default_name_8"
                value: "<your_own_value>"
            name: "default_name_10"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller.qos/fortios_switch_controller.qos_ip_dscp_map_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch QoS IP precedence/DSCP.
        fortios_switch_controller.qos_ip_dscp_map:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller.qos_ip_dscp_map:
            state: "present"
            description: "<your_own_value>"
            map:
             -
                cos-queue: "5"
                diffserv: "CS0"
                ip-precedence: "network-control"
                name: "default_name_8"
                value: "<your_own_value>"
            name: "default_name_10"




