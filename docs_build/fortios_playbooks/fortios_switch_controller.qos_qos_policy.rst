========================================
fortios_switch_controller.qos_qos_policy
========================================


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
      - name: Configure FortiSwitch QoS policy.
        fortios_switch_controller.qos_qos_policy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller.qos_qos_policy:
            state: "present"
            default-cos: "3"
            name: "default_name_4"
            queue-policy: "<your_own_value> (source switch-controller.qos.queue-policy.name)"
            trust-dot1p-map: "<your_own_value> (source switch-controller.qos.dot1p-map.name)"
            trust-ip-dscp-map: "<your_own_value> (source switch-controller.qos.ip-dscp-map.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller.qos/fortios_switch_controller.qos_qos_policy_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch QoS policy.
        fortios_switch_controller.qos_qos_policy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller.qos_qos_policy:
            state: "present"
            default-cos: "3"
            name: "default_name_4"
            queue-policy: "<your_own_value> (source switch-controller.qos.queue-policy.name)"
            trust-dot1p-map: "<your_own_value> (source switch-controller.qos.dot1p-map.name)"
            trust-ip-dscp-map: "<your_own_value> (source switch-controller.qos.ip-dscp-map.name)"




