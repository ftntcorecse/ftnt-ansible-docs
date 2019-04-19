===============================
fortios_firewall_ip_translation
===============================


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
      - name: Configure firewall IP-translation.
        fortios_firewall_ip_translation:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ip_translation:
            state: "present"
            endip: "<your_own_value>"
            map-startip: "<your_own_value>"
            startip: "<your_own_value>"
            transid: "6"
            type: "SCTP"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_ip_translation_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure firewall IP-translation.
        fortios_firewall_ip_translation:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ip_translation:
            state: "present"
            endip: "<your_own_value>"
            map-startip: "<your_own_value>"
            startip: "<your_own_value>"
            transid: "6"
            type: "SCTP"




