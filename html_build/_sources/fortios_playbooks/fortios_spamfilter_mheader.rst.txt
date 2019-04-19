==========================
fortios_spamfilter_mheader
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
      - name: Configure AntiSpam MIME header.
        fortios_spamfilter_mheader:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_mheader:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "spam"
                fieldbody: "<your_own_value>"
                fieldname: "<your_own_value>"
                id:  "8"
                pattern-type: "wildcard"
                status: "enable"
            id:  "11"
            name: "default_name_12"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/spamfilter/fortios_spamfilter_mheader_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure AntiSpam MIME header.
        fortios_spamfilter_mheader:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_mheader:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "spam"
                fieldbody: "<your_own_value>"
                fieldname: "<your_own_value>"
                id:  "8"
                pattern-type: "wildcard"
                status: "enable"
            id:  "11"
            name: "default_name_12"




