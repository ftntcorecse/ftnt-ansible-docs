=======================================
fortios_wireless_controller_utm_profile
=======================================


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
      - name: Configure UTM (Unified Threat Management) profile.
        fortios_wireless_controller_utm_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_utm_profile:
            state: "present"
            antivirus-profile: "<your_own_value> (source antivirus.profile.name)"
            application-list: "<your_own_value> (source application.list.name)"
            comment: "Comment."
            ips-sensor: "<your_own_value> (source ips.sensor.name)"
            name: "default_name_7"
            scan-botnet-connections: "disable"
            utm-log: "enable"
            webfilter-profile: "<your_own_value> (source webfilter.profile.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_utm_profile_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure UTM (Unified Threat Management) profile.
        fortios_wireless_controller_utm_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_utm_profile:
            state: "present"
            antivirus-profile: "<your_own_value> (source antivirus.profile.name)"
            application-list: "<your_own_value> (source application.list.name)"
            comment: "Comment."
            ips-sensor: "<your_own_value> (source ips.sensor.name)"
            name: "default_name_7"
            scan-botnet-connections: "disable"
            utm-log: "enable"
            webfilter-profile: "<your_own_value> (source webfilter.profile.name)"




