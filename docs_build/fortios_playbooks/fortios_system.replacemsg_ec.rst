============================
fortios_system.replacemsg_ec
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
      - name: Replacement messages.
        fortios_system.replacemsg_ec:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.replacemsg_ec:
            state: "present"
            buffer: "<your_own_value>"
            format: "none"
            header: "none"
            msg-type: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system.replacemsg/fortios_system.replacemsg_ec_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Replacement messages.
        fortios_system.replacemsg_ec:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system.replacemsg_ec:
            state: "present"
            buffer: "<your_own_value>"
            format: "none"
            header: "none"
            msg-type: "<your_own_value>"




