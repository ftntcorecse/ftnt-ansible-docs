===============================
fortios_log_null_device_setting
===============================


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
      - name: Settings for null device logging.
        fortios_log_null_device_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          log_null_device_setting:
            status: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

