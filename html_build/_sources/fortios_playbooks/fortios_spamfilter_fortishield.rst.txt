==============================
fortios_spamfilter_fortishield
==============================


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
      - name: Configure FortiGuard - AntiSpam.
        fortios_spamfilter_fortishield:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_fortishield:
            spam-submit-force: "enable"
            spam-submit-srv: "<your_own_value>"
            spam-submit-txt2htm: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/spamfilter/fortios_spamfilter_fortishield_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiGuard - AntiSpam.
        fortios_spamfilter_fortishield:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_fortishield:
            spam-submit-force: "enable"
            spam-submit-srv: "<your_own_value>"
            spam-submit-txt2htm: "enable"




