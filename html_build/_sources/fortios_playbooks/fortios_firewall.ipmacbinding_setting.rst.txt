=====================================
fortios_firewall.ipmacbinding_setting
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
      - name: Configure IP to MAC binding settings.
        fortios_firewall.ipmacbinding_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ipmacbinding_setting:
            bindthroughfw: "enable"
            bindtofw: "enable"
            undefinedhost: "allow"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.ipmacbinding/fortios_firewall.ipmacbinding_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IP to MAC binding settings.
        fortios_firewall.ipmacbinding_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ipmacbinding_setting:
            bindthroughfw: "enable"
            bindtofw: "enable"
            undefinedhost: "allow"




