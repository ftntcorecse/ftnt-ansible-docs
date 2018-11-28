=========================================
fortios_switch_controller_802_1X_settings
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
      - name: Configure global 802.1X settings.
        fortios_switch_controller_802_1X_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_802_1X_settings:
            link-down-auth: "set-unauth"
            max-reauth-attempt: "4"
            reauth-period: "5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_802_1X_settings_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure global 802.1X settings.
        fortios_switch_controller_802_1X_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_802_1X_settings:
            link-down-auth: "set-unauth"
            max-reauth-attempt: "4"
            reauth-period: "5"




