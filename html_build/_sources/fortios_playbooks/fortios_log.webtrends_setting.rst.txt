=============================
fortios_log.webtrends_setting
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
        fortios_log.webtrends_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.webtrends_setting:
            server: "192.168.100.40"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log.webtrends/fortios_log.webtrends_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Settings for WebTrends.
        fortios_log.webtrends_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.webtrends_setting:
            server: "192.168.100.40"
            status: "enable"




