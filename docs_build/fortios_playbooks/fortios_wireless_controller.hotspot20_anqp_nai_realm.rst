====================================================
fortios_wireless_controller.hotspot20_anqp_nai_realm
====================================================


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
      - name: Configure network access identifier (NAI) realm.
        fortios_wireless_controller.hotspot20_anqp_nai_realm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_nai_realm:
            state: "present"
            nai-list:
             -
                eap-method:
                 -
                    auth-param:
                     -
                        id:  "6"
                        index: "7"
                        val: "eap-identity"
                    index: "9"
                    method: "eap-identity"
                encoding: "disable"
                nai-realm: "<your_own_value>"
                name: "default_name_13"
            name: "default_name_14"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_anqp_nai_realm_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure network access identifier (NAI) realm.
        fortios_wireless_controller.hotspot20_anqp_nai_realm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_nai_realm:
            state: "present"
            nai-list:
             -
                eap-method:
                 -
                    auth-param:
                     -
                        id:  "6"
                        index: "7"
                        val: "eap-identity"
                    index: "9"
                    method: "eap-identity"
                encoding: "disable"
                nai-realm: "<your_own_value>"
                name: "default_name_13"
            name: "default_name_14"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

