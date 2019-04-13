===========================================
fortios_wireless_controller_bonjour_profile
===========================================


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
      - name: Configure Bonjour profiles. Bonjour is Apple's zero configuration networking protocol. Bonjour profiles allow APs and FortiAPs to connnect to
         networks using Bonjour.
        fortios_wireless_controller_bonjour_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_bonjour_profile:
            state: "present"
            comment: "Comment."
            name: "default_name_4"
            policy-list:
             -
                description: "<your_own_value>"
                from-vlan: "<your_own_value>"
                policy-id: "8"
                services: "all"
                to-vlan: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_bonjour_profile_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure Bonjour profiles. Bonjour is Apple's zero configuration networking protocol. Bonjour profiles allow APs and FortiAPs to connnect to networks using Bonjour.
        fortios_wireless_controller_bonjour_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_bonjour_profile:
            state: "present"
            comment: "Comment."
            name: "default_name_4"
            policy-list:
             -
                description: "<your_own_value>"
                from-vlan: "<your_own_value>"
                policy-id: "8"
                services: "all"
                to-vlan: "<your_own_value>"




