=======================
fortios_user_fortitoken
=======================


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
      - name: Configure FortiToken.
        fortios_user_fortitoken:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_fortitoken:
            state: "present"
            activation-code: "<your_own_value>"
            activation-expire: "4"
            comments: "<your_own_value>"
            license: "<your_own_value>"
            os-ver: "<your_own_value>"
            reg-id: "<your_own_value>"
            seed: "<your_own_value>"
            serial-number: "<your_own_value>"
            status: "active"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_fortitoken_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiToken.
        fortios_user_fortitoken:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_fortitoken:
            state: "present"
            activation-code: "<your_own_value>"
            activation-expire: "4"
            comments: "<your_own_value>"
            license: "<your_own_value>"
            os-ver: "<your_own_value>"
            reg-id: "<your_own_value>"
            seed: "<your_own_value>"
            serial-number: "<your_own_value>"
            status: "active"




