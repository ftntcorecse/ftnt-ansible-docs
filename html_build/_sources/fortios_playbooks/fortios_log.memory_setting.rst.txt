==========================
fortios_log.memory_setting
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
      - name: Settings for memory buffer.
        fortios_log.memory_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.memory_setting:
            diskfull: "overwrite"
            status: "enable"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/log.memory/fortios_log.memory_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Settings for memory buffer.
        fortios_log.memory_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.memory_setting:
            diskfull: "overwrite"
            status: "enable"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

