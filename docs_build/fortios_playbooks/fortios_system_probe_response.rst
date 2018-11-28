=============================
fortios_system_probe_response
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
      - name: Configure system probe response.
        fortios_system_probe_response:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_probe_response:
            http-probe-value: "<your_own_value>"
            mode: "none"
            password: "<your_own_value>"
            port: "6"
            security-mode: "none"
            timeout: "8"
            ttl-mode: "reinit"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_probe_response_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure system probe response.
        fortios_system_probe_response:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_probe_response:
            http-probe-value: "<your_own_value>"
            mode: "none"
            password: "<your_own_value>"
            port: "6"
            security-mode: "none"
            timeout: "8"
            ttl-mode: "reinit"




