================================
fortios_system_management_tunnel
================================


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
      - name: Management tunnel configuration.
        fortios_system_management_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_management_tunnel:
            allow-collect-statistics: "enable"
            allow-config-restore: "enable"
            allow-push-configuration: "enable"
            allow-push-firmware: "enable"
            authorized-manager-only: "enable"
            serial-number: "<your_own_value>"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_management_tunnel_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Management tunnel configuration.
        fortios_system_management_tunnel:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_management_tunnel:
            allow-collect-statistics: "enable"
            allow-config-restore: "enable"
            allow-push-configuration: "enable"
            allow-push-firmware: "enable"
            authorized-manager-only: "enable"
            serial-number: "<your_own_value>"
            status: "enable"




