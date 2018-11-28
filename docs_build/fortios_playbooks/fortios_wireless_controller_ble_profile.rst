=======================================
fortios_wireless_controller_ble_profile
=======================================


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
      - name: Configure Bluetooth Low Energy profile.
        fortios_wireless_controller_ble_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_ble_profile:
            state: "present"
            advertising: "ibeacon"
            beacon-interval: "4"
            ble-scanning: "enable"
            comment: "Comment."
            eddystone-instance: "<your_own_value>"
            eddystone-namespace: "<your_own_value>"
            eddystone-url: "<your_own_value>"
            eddystone-url-encode-hex: "<your_own_value>"
            ibeacon-uuid: "<your_own_value>"
            major-id: "12"
            minor-id: "13"
            name: "default_name_14"
            txpower: "0"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_ble_profile_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure Bluetooth Low Energy profile.
        fortios_wireless_controller_ble_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_ble_profile:
            state: "present"
            advertising: "ibeacon"
            beacon-interval: "4"
            ble-scanning: "enable"
            comment: "Comment."
            eddystone-instance: "<your_own_value>"
            eddystone-namespace: "<your_own_value>"
            eddystone-url: "<your_own_value>"
            eddystone-url-encode-hex: "<your_own_value>"
            ibeacon-uuid: "<your_own_value>"
            major-id: "12"
            minor-id: "13"
            name: "default_name_14"
            txpower: "0"




