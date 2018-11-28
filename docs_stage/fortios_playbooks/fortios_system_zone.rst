===================
fortios_system_zone
===================


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
      - name: Configure zones to group two or more interfaces. When a zone is created you can configure policies for the zone instead of individual interfaces in
         the zone.
        fortios_system_zone:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_zone:
            state: "present"
            interface:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            intrazone: "allow"
            name: "default_name_6"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_9"
                tags:
                 -
                    name: "default_name_11 (source system.object-tagging.tags.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_zone_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure zones to group two or more interfaces. When a zone is created you can configure policies for the zone instead of individual interfaces in the zone.
        fortios_system_zone:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_zone:
            state: "present"
            interface:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            intrazone: "allow"
            name: "default_name_6"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_9"
                tags:
                 -
                    name: "default_name_11 (source system.object-tagging.tags.name)"




