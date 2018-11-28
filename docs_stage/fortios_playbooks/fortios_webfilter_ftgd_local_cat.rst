================================
fortios_webfilter_ftgd_local_cat
================================


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
      - name: Configure FortiGuard Web Filter local categories.
        fortios_webfilter_ftgd_local_cat:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_ftgd_local_cat:
            state: "present"
            desc: "<your_own_value>"
            id:  "4"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/webfilter/fortios_webfilter_ftgd_local_cat_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FortiGuard Web Filter local categories.
        fortios_webfilter_ftgd_local_cat:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_ftgd_local_cat:
            state: "present"
            desc: "<your_own_value>"
            id:  "4"
            status: "enable"




