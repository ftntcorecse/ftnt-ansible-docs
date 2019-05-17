===================
fortios_icap_server
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
      - name: Configure ICAP servers.
        fortios_icap_server:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          icap_server:
            state: "present"
            ip-address: "<your_own_value>"
            ip-version: "4"
            ip6-address: "<your_own_value>"
            max-connections: "6"
            name: "default_name_7"
            port: "8"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

