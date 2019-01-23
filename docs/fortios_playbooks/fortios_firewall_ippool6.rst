========================
fortios_firewall_ippool6
========================


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
      - name: Configure IPv6 IP pools.
        fortios_firewall_ippool6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_ippool6:
            state: "present"
            comments: "<your_own_comment>"
            endip: "<your_own_value>"
            name: "default_name_5"
            startip: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

