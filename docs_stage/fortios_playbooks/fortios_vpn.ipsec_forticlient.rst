=============================
fortios_vpn.ipsec_forticlient
=============================


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
      - name: Configure FortiClient policy realm.
        fortios_vpn.ipsec_forticlient:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ipsec_forticlient:
            state: "present"
            phase2name: "<your_own_value> (source vpn.ipsec.phase2.name vpn.ipsec.phase2-interface.name)"
            realm: "<your_own_value>"
            status: "enable"
            usergroupname: "<your_own_value> (source user.group.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.ipsec/fortios_vpn.ipsec_forticlient_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiClient policy realm.
        fortios_vpn.ipsec_forticlient:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ipsec_forticlient:
            state: "present"
            phase2name: "<your_own_value> (source vpn.ipsec.phase2.name vpn.ipsec.phase2-interface.name)"
            realm: "<your_own_value>"
            status: "enable"
            usergroupname: "<your_own_value> (source user.group.name)"




