======================
fortios_system_fips_cc
======================


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
      - name: Configure FIPS-CC mode.
        fortios_system_fips_cc:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fips_cc:
            entropy-token: "enable"
            key-generation-self-test: "enable"
            self-test-period: "5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_fips_cc_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FIPS-CC mode.
        fortios_system_fips_cc:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_fips_cc:
            entropy-token: "enable"
            key-generation-self-test: "enable"
            self-test-period: "5"




