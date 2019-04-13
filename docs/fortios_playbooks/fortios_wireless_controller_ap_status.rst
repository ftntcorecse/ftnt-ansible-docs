=====================================
fortios_wireless_controller_ap_status
=====================================


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
      - name: Configure access point status (rogue | accepted | suppressed).
        fortios_wireless_controller_ap_status:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_ap_status:
            state: "present"
            bssid: "<your_own_value>"
            id:  "4"
            ssid: "<your_own_value>"
            status: "rogue"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_ap_status_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure access point status (rogue | accepted | suppressed).
        fortios_wireless_controller_ap_status:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_ap_status:
            state: "present"
            bssid: "<your_own_value>"
            id:  "4"
            ssid: "<your_own_value>"
            status: "rogue"




