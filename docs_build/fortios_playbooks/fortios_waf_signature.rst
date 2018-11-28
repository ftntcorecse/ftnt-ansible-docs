=====================
fortios_waf_signature
=====================


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
      - name: Hidden table for datasource.
        fortios_waf_signature:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          waf_signature:
            state: "present"
            desc: "<your_own_value>"
            id:  "4"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/waf/fortios_waf_signature_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Hidden table for datasource.
        fortios_waf_signature:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          waf_signature:
            state: "present"
            desc: "<your_own_value>"
            id:  "4"




