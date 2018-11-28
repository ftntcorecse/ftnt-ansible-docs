======================================================
fortios_endpoint_control_forticlient_registration_sync
======================================================


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
      - name: Configure FortiClient registration synchronization settings.
        fortios_endpoint_control_forticlient_registration_sync:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_forticlient_registration_sync:
            state: "present"
            peer-ip: "<your_own_value>"
            peer-name: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/endpoint_control/fortios_endpoint_control_forticlient_registration_sync_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiClient registration synchronization settings.
        fortios_endpoint_control_forticlient_registration_sync:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_forticlient_registration_sync:
            state: "present"
            peer-ip: "<your_own_value>"
            peer-name: "<your_own_value>"




