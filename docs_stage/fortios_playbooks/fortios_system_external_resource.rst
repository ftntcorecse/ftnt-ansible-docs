================================
fortios_system_external_resource
================================


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
      - name: Configure external resource.
        fortios_system_external_resource:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_external_resource:
            state: "present"
            category: "3"
            comments: "<your_own_value>"
            name: "default_name_5"
            refresh-rate: "6"
            resource: "<your_own_value>"
            status: "enable"
            type: "category"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_external_resource_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure external resource.
        fortios_system_external_resource:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_external_resource:
            state: "present"
            category: "3"
            comments: "<your_own_value>"
            name: "default_name_5"
            refresh-rate: "6"
            resource: "<your_own_value>"
            status: "enable"
            type: "category"




