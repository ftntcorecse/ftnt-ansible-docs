============================
fortios_user_device_category
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
      - name: Configure device categories.
        fortios_user_device_category:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_device_category:
            state: "present"
            comment: "Comment."
            desc: "<your_own_value>"
            name: "default_name_5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_device_category_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure device categories.
        fortios_user_device_category:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_device_category:
            state: "present"
            comment: "Comment."
            desc: "<your_own_value>"
            name: "default_name_5"




