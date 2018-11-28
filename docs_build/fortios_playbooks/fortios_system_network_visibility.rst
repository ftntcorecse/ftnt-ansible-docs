=================================
fortios_system_network_visibility
=================================


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
      - name: Configure network visibility settings.
        fortios_system_network_visibility:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_network_visibility:
            destination-hostname-visibility: "disable"
            destination-location: "disable"
            destination-visibility: "disable"
            hostname-limit: "6"
            hostname-ttl: "7"
            source-location: "disable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_network_visibility_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure network visibility settings.
        fortios_system_network_visibility:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_network_visibility:
            destination-hostname-visibility: "disable"
            destination-location: "disable"
            destination-visibility: "disable"
            hostname-limit: "6"
            hostname-ttl: "7"
            source-location: "disable"




