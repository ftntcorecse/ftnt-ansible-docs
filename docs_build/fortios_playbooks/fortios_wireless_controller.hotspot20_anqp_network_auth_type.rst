============================================================
fortios_wireless_controller.hotspot20_anqp_network_auth_type
============================================================


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
      - name: Configure network authentication type.
        fortios_wireless_controller.hotspot20_anqp_network_auth_type:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_network_auth_type:
            state: "present"
            auth-type: "acceptance-of-terms"
            name: "default_name_4"
            url: "myurl.com"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_anqp_network_auth_type_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure network authentication type.
        fortios_wireless_controller.hotspot20_anqp_network_auth_type:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_network_auth_type:
            state: "present"
            auth-type: "acceptance-of-terms"
            name: "default_name_4"
            url: "myurl.com"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

