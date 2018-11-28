=========================
fortios_vpn.ssl.web_realm
=========================


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
      - name: Realm.
        fortios_vpn.ssl.web_realm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ssl.web_realm:
            state: "present"
            login-page: "<your_own_value>"
            max-concurrent-user: "4"
            url-path: "<your_own_value>"
            virtual-host: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.ssl.web/fortios_vpn.ssl.web_realm_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Realm.
        fortios_vpn.ssl.web_realm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ssl.web_realm:
            state: "present"
            login-page: "<your_own_value>"
            max-concurrent-user: "4"
            url-path: "<your_own_value>"
            virtual-host: "<your_own_value>"




