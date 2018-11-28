==============================
fortios_system_custom_language
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
      - name: Configure custom languages.
        fortios_system_custom_language:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_custom_language:
            state: "present"
            comments: "<your_own_value>"
            filename: "<your_own_value>"
            name: "default_name_5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_custom_language_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure custom languages.
        fortios_system_custom_language:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_custom_language:
            state: "present"
            comments: "<your_own_value>"
            filename: "<your_own_value>"
            name: "default_name_5"




