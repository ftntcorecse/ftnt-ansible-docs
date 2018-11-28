=====================================
fortios_wireless_controller_vap_group
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
      - name: Configure virtual Access Point (VAP) groups.
        fortios_wireless_controller_vap_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_vap_group:
            state: "present"
            comment: "Comment."
            name: "default_name_4"
            vaps:
             -
                name: "default_name_6 (source wireless-controller.vap.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_vap_group_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure virtual Access Point (VAP) groups.
        fortios_wireless_controller_vap_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_vap_group:
            state: "present"
            comment: "Comment."
            name: "default_name_4"
            vaps:
             -
                name: "default_name_6 (source wireless-controller.vap.name)"




