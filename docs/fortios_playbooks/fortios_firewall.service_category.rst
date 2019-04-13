=================================
fortios_firewall.service_category
=================================


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
      - name: Configure service categories.
        fortios_firewall.service_category:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.service_category:
            state: "present"
            comment: "Comment."
            name: "default_name_4"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.service/fortios_firewall.service_category_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure service categories.
        fortios_firewall.service_category:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.service_category:
            state: "present"
            comment: "Comment."
            name: "default_name_4"




