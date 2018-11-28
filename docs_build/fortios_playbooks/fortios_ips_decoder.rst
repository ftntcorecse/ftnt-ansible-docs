===================
fortios_ips_decoder
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
      - name: Configure IPS decoder.
        fortios_ips_decoder:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_decoder:
            state: "present"
            name: "default_name_3"
            parameter:
             -
                name: "default_name_5"
                value: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/ips/fortios_ips_decoder_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS decoder.
        fortios_ips_decoder:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ips_decoder:
            state: "present"
            name: "default_name_3"
            parameter:
             -
                name: "default_name_5"
                value: "<your_own_value>"




