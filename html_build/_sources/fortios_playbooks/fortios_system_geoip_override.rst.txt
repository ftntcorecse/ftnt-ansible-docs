=============================
fortios_system_geoip_override
=============================


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
      - name: Configure geographical location mapping for IP address(es) to override mappings from FortiGuard.
        fortios_system_geoip_override:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_geoip_override:
            state: "present"
            country-id: "<your_own_value>"
            description: "<your_own_value>"
            ip-range:
             -
                end-ip: "<your_own_value>"
                id:  "7"
                start-ip: "<your_own_value>"
            name: "default_name_9"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_geoip_override_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure geographical location mapping for IP address(es) to override mappings from FortiGuard.
        fortios_system_geoip_override:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_geoip_override:
            state: "present"
            country-id: "<your_own_value>"
            description: "<your_own_value>"
            ip-range:
             -
                end-ip: "<your_own_value>"
                id:  "7"
                start-ip: "<your_own_value>"
            name: "default_name_9"




