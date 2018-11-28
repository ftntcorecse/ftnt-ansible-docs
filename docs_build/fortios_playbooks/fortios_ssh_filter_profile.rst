==========================
fortios_ssh_filter_profile
==========================


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
      - name: SSH filter profile.
        fortios_ssh_filter_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ssh_filter_profile:
            state: "present"
            block: "x11"
            default-command-log: "enable"
            log: "x11"
            name: "default_name_6"
            shell-commands:
             -
                action: "block"
                alert: "enable"
                id:  "10"
                log: "enable"
                pattern: "<your_own_value>"
                severity: "low"
                type: "simple"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/ssh_filter/fortios_ssh_filter_profile_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SSH filter profile.
        fortios_ssh_filter_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ssh_filter_profile:
            state: "present"
            block: "x11"
            default-command-log: "enable"
            log: "x11"
            name: "default_name_6"
            shell-commands:
             -
                action: "block"
                alert: "enable"
                id:  "10"
                log: "enable"
                pattern: "<your_own_value>"
                severity: "low"
                type: "simple"




