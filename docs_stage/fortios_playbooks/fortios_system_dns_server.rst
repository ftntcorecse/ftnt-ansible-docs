=========================
fortios_system_dns_server
=========================


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
      - name: Configure DNS servers.
        fortios_system_dns_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dns_server:
            state: "present"
            dnsfilter-profile: "<your_own_value> (source dnsfilter.profile.name)"
            mode: "recursive"
            name: "default_name_5 (source system.interface.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_dns_server_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure DNS servers.
        fortios_system_dns_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_dns_server:
            state: "present"
            dnsfilter-profile: "<your_own_value> (source dnsfilter.profile.name)"
            mode: "recursive"
            name: "default_name_5 (source system.interface.name)"




