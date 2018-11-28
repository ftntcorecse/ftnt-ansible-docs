=======================
fortios_wanopt_settings
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
      - name: Configure WAN optimization settings.
        fortios_wanopt_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wanopt_settings:
            auto-detect-algorithm: "simple"
            host-id: "myhostname"
            tunnel-ssl-algorithm: "low"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wanopt/fortios_wanopt_settings_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure WAN optimization settings.
        fortios_wanopt_settings:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wanopt_settings:
            auto-detect-algorithm: "simple"
            host-id: "myhostname"
            tunnel-ssl-algorithm: "low"




