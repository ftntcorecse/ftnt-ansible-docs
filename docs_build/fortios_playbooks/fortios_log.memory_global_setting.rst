=================================
fortios_log.memory_global_setting
=================================


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
      - name: Global settings for memory logging.
        fortios_log.memory_global_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.memory_global_setting:
            full-final-warning-threshold: "3"
            full-first-warning-threshold: "4"
            full-second-warning-threshold: "5"
            max-size: "6"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log.memory/fortios_log.memory_global_setting_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Global settings for memory logging.
        fortios_log.memory_global_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.memory_global_setting:
            full-final-warning-threshold: "3"
            full-first-warning-threshold: "4"
            full-second-warning-threshold: "5"
            max-size: "6"




