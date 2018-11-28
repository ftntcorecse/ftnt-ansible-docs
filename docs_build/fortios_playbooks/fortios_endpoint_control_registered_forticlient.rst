===============================================
fortios_endpoint_control_registered_forticlient
===============================================


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
      - name: Registered FortiClient list.
        fortios_endpoint_control_registered_forticlient:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_registered_forticlient:
            state: "present"
            flag: "3"
            ip: "<your_own_value>"
            mac: "<your_own_value>"
            reg-fortigate: "<your_own_value>"
            status: "7"
            uid: "<your_own_value>"
            vdom: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/endpoint_control/fortios_endpoint_control_registered_forticlient_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Registered FortiClient list.
        fortios_endpoint_control_registered_forticlient:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_registered_forticlient:
            state: "present"
            flag: "3"
            ip: "<your_own_value>"
            mac: "<your_own_value>"
            reg-fortigate: "<your_own_value>"
            status: "7"
            uid: "<your_own_value>"
            vdom: "<your_own_value>"




