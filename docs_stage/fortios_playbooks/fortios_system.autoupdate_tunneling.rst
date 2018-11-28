===================================
fortios_system.autoupdate_tunneling
===================================


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
      - name: Configure web proxy tunnelling for the FDN.
        fortios_system.autoupdate_tunneling:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.autoupdate_tunneling:
            address: "<your_own_value>"
            password: "<your_own_value>"
            port: "5"
            status: "enable"
            username: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system.autoupdate/fortios_system.autoupdate_tunneling_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure web proxy tunnelling for the FDN.
        fortios_system.autoupdate_tunneling:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.autoupdate_tunneling:
            address: "<your_own_value>"
            password: "<your_own_value>"
            port: "5"
            status: "enable"
            username: "<your_own_value>"




