==================
fortios_system_csf
==================


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
      - name: Add this FortiGate to a Security Fabric or set up a new Security Fabric on this FortiGate.
        fortios_system_csf:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_csf:
            configuration-sync: "default"
            fabric-device:
             -
                device-ip: "<your_own_value>"
                device-type: "fortimail"
                login: "<your_own_value>"
                name: "default_name_8"
                password: "<your_own_value>"
            fixed-key: "<your_own_value>"
            group-name: "<your_own_value>"
            group-password: "<your_own_value>"
            management-ip: "<your_own_value>"
            management-port: "14"
            status: "enable"
            trusted-list:
             -
                action: "accept"
                downstream-authorization: "enable"
                ha-members: "<your_own_value>"
                serial: "<your_own_value>"
            upstream-ip: "<your_own_value>"
            upstream-port: "22"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_csf_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Add this FortiGate to a Security Fabric or set up a new Security Fabric on this FortiGate.
        fortios_system_csf:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_csf:
            configuration-sync: "default"
            fabric-device:
             -
                device-ip: "<your_own_value>"
                device-type: "fortimail"
                login: "<your_own_value>"
                name: "default_name_8"
                password: "<your_own_value>"
            fixed-key: "<your_own_value>"
            group-name: "<your_own_value>"
            group-password: "<your_own_value>"
            management-ip: "<your_own_value>"
            management-port: "14"
            status: "enable"
            trusted-list:
             -
                action: "accept"
                downstream-authorization: "enable"
                ha-members: "<your_own_value>"
                serial: "<your_own_value>"
            upstream-ip: "<your_own_value>"
            upstream-port: "22"




