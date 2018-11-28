===========================
fortios_system.snmp_sysinfo
===========================


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
      - name: SNMP system info configuration.
        fortios_system.snmp_sysinfo:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.snmp_sysinfo:
            contact-info: "<your_own_value>"
            description: "<your_own_value>"
            engine-id: "<your_own_value>"
            location: "<your_own_value>"
            status: "enable"
            trap-high-cpu-threshold: "8"
            trap-log-full-threshold: "9"
            trap-low-memory-threshold: "10"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system.snmp/fortios_system.snmp_sysinfo_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SNMP system info configuration.
        fortios_system.snmp_sysinfo:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.snmp_sysinfo:
            contact-info: "<your_own_value>"
            description: "<your_own_value>"
            engine-id: "<your_own_value>"
            location: "<your_own_value>"
            status: "enable"
            trap-high-cpu-threshold: "8"
            trap-log-full-threshold: "9"
            trap-low-memory-threshold: "10"




