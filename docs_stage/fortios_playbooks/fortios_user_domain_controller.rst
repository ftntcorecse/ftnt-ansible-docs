==============================
fortios_user_domain_controller
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
      - name: Configure domain controller entries.
        fortios_user_domain_controller:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_domain_controller:
            state: "present"
            domain-name: "<your_own_value>"
            ip-address: "<your_own_value>"
            ldap-server: "<your_own_value> (source user.ldap.name)"
            name: "default_name_6"
            port: "7"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_domain_controller_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure domain controller entries.
        fortios_user_domain_controller:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_domain_controller:
            state: "present"
            domain-name: "<your_own_value>"
            ip-address: "<your_own_value>"
            ldap-server: "<your_own_value> (source user.ldap.name)"
            name: "default_name_6"
            port: "7"




