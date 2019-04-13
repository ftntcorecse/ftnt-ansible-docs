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
<<<<<<< Updated upstream
            comments: "<your_own_value>"
=======
            comments: "<your_own_comment>"
>>>>>>> Stashed changes
            endip: "<your_own_value>"
            name: "default_name_5"
            startip: "<your_own_value>"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/firewall/fortios_firewall_ippool6_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

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
            comments: "<your_own_value>"
            endip: "<your_own_value>"
            name: "default_name_5"
            startip: "<your_own_value>"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

