======================
fortios_report_setting
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
      - name: Report setting configuration.
        fortios_report_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          report_setting:
            fortiview: "enable"
            pdf-report: "enable"
            report-source: "forward-traffic"
            top-n: "6"
            web-browsing-threshold: "7"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/report/fortios_report_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Report setting configuration.
        fortios_report_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          report_setting:
            fortiview: "enable"
            pdf-report: "enable"
            report-source: "forward-traffic"
            top-n: "6"
            web-browsing-threshold: "7"




