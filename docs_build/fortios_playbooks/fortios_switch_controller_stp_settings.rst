======================================
fortios_switch_controller_stp_settings
======================================


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
      - name: Configure FortiSwitch spanning tree protocol (STP).
        fortios_switch_controller_stp_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_stp_settings:
            forward-time: "3"
            hello-time: "4"
            max-age: "5"
            max-hops: "6"
            name: "default_name_7"
            pending-timer: "8"
            revision: "9"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_stp_settings_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiSwitch spanning tree protocol (STP).
        fortios_switch_controller_stp_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_stp_settings:
            forward-time: "3"
            hello-time: "4"
            max-age: "5"
            max-hops: "6"
            name: "default_name_7"
            pending-timer: "8"
            revision: "9"
            status: "enable"




