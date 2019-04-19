========================================================
fortios_wireless_controller.hotspot20_h2qp_operator_name
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
      - name: Configure operator friendly name.
        fortios_wireless_controller.hotspot20_h2qp_operator_name:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_h2qp_operator_name:
            state: "present"
            name: "default_name_3"
            value-list:
             -
                index: "5"
                lang: "<your_own_value>"
                value: "<your_own_value>"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_h2qp_operator_name_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure operator friendly name.
        fortios_wireless_controller.hotspot20_h2qp_operator_name:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_h2qp_operator_name:
            state: "present"
            name: "default_name_3"
            value-list:
             -
                index: "5"
                lang: "<your_own_value>"
                value: "<your_own_value>"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

