==========================================
fortios_system_password_policy_guest_admin
==========================================


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
      - name: Configure the password policy for guest administrators.
        fortios_system_password_policy_guest_admin:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_password_policy_guest_admin:
            apply-to: "guest-admin-password"
            change-4-characters: "enable"
            expire-day: "5"
            expire-status: "enable"
            min-lower-case-letter: "7"
            min-non-alphanumeric: "8"
            min-number: "9"
            min-upper-case-letter: "10"
            minimum-length: "11"
            reuse-password: "enable"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_password_policy_guest_admin_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure the password policy for guest administrators.
        fortios_system_password_policy_guest_admin:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_password_policy_guest_admin:
            apply-to: "guest-admin-password"
            change-4-characters: "enable"
            expire-day: "5"
            expire-status: "enable"
            min-lower-case-letter: "7"
            min-non-alphanumeric: "8"
            min-number: "9"
            min-upper-case-letter: "10"
            minimum-length: "11"
            reuse-password: "enable"
            status: "enable"




