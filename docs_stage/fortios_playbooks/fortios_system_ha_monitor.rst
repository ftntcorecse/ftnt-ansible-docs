=========================
fortios_system_ha_monitor
=========================


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
      - name: Configure HA monitor.
        fortios_system_ha_monitor:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ha_monitor:
            monitor-vlan: "enable"
            vlan-hb-interval: "4"
            vlan-hb-lost-threshold: "5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_ha_monitor_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure HA monitor.
        fortios_system_ha_monitor:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ha_monitor:
            monitor-vlan: "enable"
            vlan-hb-interval: "4"
            vlan-hb-lost-threshold: "5"




