==============================
fortios_vpn.ipsec_concentrator
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
      - name: Concentrator configuration.
        fortios_vpn.ipsec_concentrator:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ipsec_concentrator:
            state: "present"
            member:
             -
                name: "default_name_4 (source vpn.ipsec.manualkey.name vpn.ipsec.phase1.name)"
            name: "default_name_5"
            src-check: "disable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.ipsec/fortios_vpn.ipsec_concentrator_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Concentrator configuration.
        fortios_vpn.ipsec_concentrator:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ipsec_concentrator:
            state: "present"
            member:
             -
                name: "default_name_4 (source vpn.ipsec.manualkey.name vpn.ipsec.phase1.name)"
            name: "default_name_5"
            src-check: "disable"




