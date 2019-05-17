=====================================
fortios_firewall_ipmacbinding_setting
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
        fortios_firewall_ipmacbinding_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ipmacbinding_setting:
            bindthroughfw: "enable"
            bindtofw: "enable"
            undefinedhost: "allow"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

