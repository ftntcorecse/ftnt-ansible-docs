=============================
fortios_log_webtrends_setting
=============================


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
      - name: Settings for WebTrends.
        fortios_log_webtrends_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          log_webtrends_setting:
            server: "192.168.100.40"
            status: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

