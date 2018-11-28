========================================================
fortios_wireless_controller.hotspot20_anqp_3gpp_cellular
========================================================


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
      - name: Configure 3GPP public land mobile network (PLMN).
        fortios_wireless_controller.hotspot20_anqp_3gpp_cellular:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_3gpp_cellular:
            state: "present"
            mcc-mnc-list:
             -
                id:  "4"
                mcc: "<your_own_value>"
                mnc: "<your_own_value>"
            name: "default_name_7"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_anqp_3gpp_cellular_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure 3GPP public land mobile network (PLMN).
        fortios_wireless_controller.hotspot20_anqp_3gpp_cellular:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_3gpp_cellular:
            state: "present"
            mcc-mnc-list:
             -
                id:  "4"
                mcc: "<your_own_value>"
                mnc: "<your_own_value>"
            name: "default_name_7"




