===============================
fortios_endpoint_control_client
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
      - name: Configure endpoint control client lists.
        fortios_endpoint_control_client:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_client:
            state: "present"
            ad-groups: "<your_own_value>"
            ftcl-uid: "<your_own_value>"
            id:  "5"
            info: "<your_own_value>"
            src-ip: "<your_own_value>"
            src-mac: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/endpoint_control/fortios_endpoint_control_client_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure endpoint control client lists.
        fortios_endpoint_control_client:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_client:
            state: "present"
            ad-groups: "<your_own_value>"
            ftcl-uid: "<your_own_value>"
            id:  "5"
            info: "<your_own_value>"
            src-ip: "<your_own_value>"
            src-mac: "<your_own_value>"




