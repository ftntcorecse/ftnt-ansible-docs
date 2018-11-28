==========================
fortios_application_custom
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
      - name: Configure custom application signatures.
        fortios_application_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          application_custom:
            state: "present"
            behavior: "<your_own_value>"
            category: "4"
            comment: "Comment."
            id:  "6"
            name: "default_name_7"
            protocol: "<your_own_value>"
            signature: "<your_own_value>"
            tag: "<your_own_value>"
            technology: "<your_own_value>"
            vendor: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/application/fortios_application_custom_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure custom application signatures.
        fortios_application_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          application_custom:
            state: "present"
            behavior: "<your_own_value>"
            category: "4"
            comment: "Comment."
            id:  "6"
            name: "default_name_7"
            protocol: "<your_own_value>"
            signature: "<your_own_value>"
            tag: "<your_own_value>"
            technology: "<your_own_value>"
            vendor: "<your_own_value>"




