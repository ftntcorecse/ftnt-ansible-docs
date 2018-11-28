====================================
fortios_firewall.wildcard_fqdn_group
====================================


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
      - name: Config global Wildcard FQDN address groups.
        fortios_firewall.wildcard_fqdn_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.wildcard_fqdn_group:
            state: "present"
            color: "3"
            comment: "Comment."
            member:
             -
                name: "default_name_6 (source firewall.wildcard-fqdn.custom.name)"
            name: "default_name_7"
            uuid: "<your_own_value>"
            visibility: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.wildcard_fqdn/fortios_firewall.wildcard_fqdn_group_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Config global Wildcard FQDN address groups.
        fortios_firewall.wildcard_fqdn_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.wildcard_fqdn_group:
            state: "present"
            color: "3"
            comment: "Comment."
            member:
             -
                name: "default_name_6 (source firewall.wildcard-fqdn.custom.name)"
            name: "default_name_7"
            uuid: "<your_own_value>"
            visibility: "enable"




