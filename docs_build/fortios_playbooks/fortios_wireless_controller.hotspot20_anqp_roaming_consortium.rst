=============================================================
fortios_wireless_controller.hotspot20_anqp_roaming_consortium
=============================================================


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
      - name: Configure roaming consortium.
        fortios_wireless_controller.hotspot20_anqp_roaming_consortium:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_roaming_consortium:
            state: "present"
            name: "default_name_3"
            oi-list:
             -
                comment: "Comment."
                index: "6"
                oi: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_anqp_roaming_consortium_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure roaming consortium.
        fortios_wireless_controller.hotspot20_anqp_roaming_consortium:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_roaming_consortium:
            state: "present"
            name: "default_name_3"
            oi-list:
             -
                comment: "Comment."
                index: "6"
                oi: "<your_own_value>"




