==============================
fortios_firewall.ssh_local_key
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
      - name: SSH proxy local keys.
        fortios_firewall.ssh_local_key:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ssh_local_key:
            state: "present"
            name: "default_name_3"
            password: "<your_own_value>"
            private-key: "<your_own_value>"
            public-key: "<your_own_value>"
            source: "built-in"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.ssh/fortios_firewall.ssh_local_key_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SSH proxy local keys.
        fortios_firewall.ssh_local_key:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ssh_local_key:
            state: "present"
            name: "default_name_3"
            password: "<your_own_value>"
            private-key: "<your_own_value>"
            public-key: "<your_own_value>"
            source: "built-in"




