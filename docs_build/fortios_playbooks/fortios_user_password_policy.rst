============================
fortios_user_password_policy
============================


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
      - name: Configure user password policy.
        fortios_user_password_policy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_password_policy:
            state: "present"
            expire-days: "3"
            name: "default_name_4"
            warn-days: "5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_password_policy_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure user password policy.
        fortios_user_password_policy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_password_policy:
            state: "present"
            expire-days: "3"
            name: "default_name_4"
            warn-days: "5"




