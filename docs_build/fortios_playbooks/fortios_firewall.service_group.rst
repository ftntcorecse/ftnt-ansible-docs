==============================
fortios_firewall.service_group
==============================


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
      - name: Configure service groups.
        fortios_firewall.service_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.service_group:
            state: "present"
            color: "3"
            comment: "Comment."
            member:
             -
                name: "default_name_6 (source firewall.service.custom.name firewall.service.group.name)"
            name: "default_name_7"
            proxy: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.service/fortios_firewall.service_group_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure service groups.
        fortios_firewall.service_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.service_group:
            state: "present"
            color: "3"
            comment: "Comment."
            member:
             -
                name: "default_name_6 (source firewall.service.custom.name firewall.service.group.name)"
            name: "default_name_7"
            proxy: "enable"




