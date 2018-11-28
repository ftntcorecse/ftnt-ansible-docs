=======================
fortios_user_krb_keytab
=======================


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
      - name: Configure Kerberos keytab entries.
        fortios_user_krb_keytab:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_krb_keytab:
            state: "present"
            keytab: "<your_own_value>"
            ldap-server: "<your_own_value> (source user.ldap.name)"
            name: "default_name_5"
            principal: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_krb_keytab_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure Kerberos keytab entries.
        fortios_user_krb_keytab:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_krb_keytab:
            state: "present"
            keytab: "<your_own_value>"
            ldap-server: "<your_own_value> (source user.ldap.name)"
            name: "default_name_5"
            principal: "<your_own_value>"




