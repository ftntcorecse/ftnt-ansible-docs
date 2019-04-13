==========================================
fortios_wireless_controller.hotspot20_icon
==========================================


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
      - name: Configure OSU provider icon.
        fortios_wireless_controller.hotspot20_icon:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_icon:
            state: "present"
            icon-list:
             -
                file: "<your_own_value>"
                height: "5"
                lang: "<your_own_value>"
                name: "default_name_7"
                type: "bmp"
                width: "9"
            name: "default_name_10"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_icon_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure OSU provider icon.
        fortios_wireless_controller.hotspot20_icon:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_icon:
            state: "present"
            icon-list:
             -
                file: "<your_own_value>"
                height: "5"
                lang: "<your_own_value>"
                name: "default_name_7"
                type: "bmp"
                width: "9"
            name: "default_name_10"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

