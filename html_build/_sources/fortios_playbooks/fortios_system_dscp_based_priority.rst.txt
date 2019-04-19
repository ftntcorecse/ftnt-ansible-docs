==================================
fortios_system_dscp_based_priority
==================================


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
      - name: Configure DSCP based priority table.
        fortios_system_dscp_based_priority:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dscp_based_priority:
            state: "present"
            ds: "3"
            id:  "4"
            priority: "low"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_dscp_based_priority_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure DSCP based priority table.
        fortios_system_dscp_based_priority:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dscp_based_priority:
            state: "present"
            ds: "3"
            id:  "4"
            priority: "low"




