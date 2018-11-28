=================
fortios_system_fm
=================


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
      - name: Configure FM.
        fortios_system_fm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fm:
            auto-backup: "enable"
            id:  "4"
            ip: "<your_own_value>"
            ipsec: "enable"
            scheduled-config-restore: "enable"
            status: "enable"
            vdom: "<your_own_value> (source system.vdom.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_fm_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FM.
        fortios_system_fm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fm:
            auto-backup: "enable"
            id:  "4"
            ip: "<your_own_value>"
            ipsec: "enable"
            scheduled-config-restore: "enable"
            status: "enable"
            vdom: "<your_own_value> (source system.vdom.name)"




