=========================
fortios_user_device_group
=========================


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
      - name: Configure device groups.
        fortios_user_device_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_device_group:
            state: "present"
            comment: "Comment."
            member:
             -
                name: "default_name_5 (source user.device.alias user.device-category.name)"
            name: "default_name_6"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_9"
                tags:
                 -
                    name: "default_name_11 (source system.object-tagging.tags.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_device_group_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure device groups.
        fortios_user_device_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_device_group:
            state: "present"
            comment: "Comment."
            member:
             -
                name: "default_name_5 (source user.device.alias user.device-category.name)"
            name: "default_name_6"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_9"
                tags:
                 -
                    name: "default_name_11 (source system.object-tagging.tags.name)"




