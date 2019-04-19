===================================
fortios_wireless_controller_setting
===================================


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
      - name: VDOM wireless controller configuration.
        fortios_wireless_controller_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_setting:
            account-id: "<your_own_value>"
            country: "NA"
            duplicate-ssid: "enable"
            fapc-compatibility: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: VDOM wireless controller configuration.
        fortios_wireless_controller_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_setting:
            account-id: "<your_own_value>"
            country: "NA"
            duplicate-ssid: "enable"
            fapc-compatibility: "enable"




