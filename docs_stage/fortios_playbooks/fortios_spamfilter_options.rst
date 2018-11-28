==========================
fortios_spamfilter_options
==========================


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
      - name: Configure AntiSpam options.
        fortios_spamfilter_options:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_options:
            dns-timeout: "3"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/spamfilter/fortios_spamfilter_options_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure AntiSpam options.
        fortios_spamfilter_options:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_options:
            dns-timeout: "3"




