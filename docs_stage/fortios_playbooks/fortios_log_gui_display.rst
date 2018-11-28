=======================
fortios_log_gui_display
=======================


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
      - name: Configure how log messages are displayed on the GUI.
        fortios_log_gui_display:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log_gui_display:
            fortiview-unscanned-apps: "enable"
            resolve-apps: "enable"
            resolve-hosts: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log/fortios_log_gui_display_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure how log messages are displayed on the GUI.
        fortios_log_gui_display:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log_gui_display:
            fortiview-unscanned-apps: "enable"
            resolve-apps: "enable"
            resolve-hosts: "enable"




