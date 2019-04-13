=======================================
fortios_firewall_internet_service_group
=======================================


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
      - name: Configure group of Internet Service.
        fortios_firewall_internet_service_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_internet_service_group:
            state: "present"
            comment: "Comment."
            member:
             -
                id:  "5 (source firewall.internet-service.id)"
            name: "default_name_6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_internet_service_group_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure group of Internet Service.
        fortios_firewall_internet_service_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_internet_service_group:
            state: "present"
            comment: "Comment."
            member:
             -
                id:  "5 (source firewall.internet-service.id)"
            name: "default_name_6"




