=====================================
fortios_firewall.wildcard_fqdn_custom
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
      - name: Config global/VDOM Wildcard FQDN address.
        fortios_firewall.wildcard_fqdn_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.wildcard_fqdn_custom:
            state: "present"
            color: "3"
            comment: "Comment."
            name: "default_name_5"
            uuid: "<your_own_value>"
            visibility: "enable"
            wildcard-fqdn: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.wildcard_fqdn/fortios_firewall.wildcard_fqdn_custom_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Config global/VDOM Wildcard FQDN address.
        fortios_firewall.wildcard_fqdn_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.wildcard_fqdn_custom:
            state: "present"
            color: "3"
            comment: "Comment."
            name: "default_name_5"
            uuid: "<your_own_value>"
            visibility: "enable"
            wildcard-fqdn: "<your_own_value>"




