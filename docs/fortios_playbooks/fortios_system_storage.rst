======================
fortios_system_storage
======================


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
      - name: Configure logical storage.
        fortios_system_storage:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_storage:
            state: "present"
            device: "<your_own_value>"
            media-status: "enable"
            name: "default_name_5"
            order: "6"
            partition: "<your_own_value>"
            size: "8"
            status: "enable"
            usage: "mix"
            wanopt-mode: "mix"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_storage_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure logical storage.
        fortios_system_storage:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_storage:
            state: "present"
            device: "<your_own_value>"
            media-status: "enable"
            name: "default_name_5"
            order: "6"
            partition: "<your_own_value>"
            size: "8"
            status: "enable"
            usage: "mix"
            wanopt-mode: "mix"




