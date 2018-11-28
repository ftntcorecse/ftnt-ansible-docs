========================
fortios_spamfilter_bword
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
      - name: Configure AntiSpam banned word list.
        fortios_spamfilter_bword:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_bword:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "spam"
                id:  "6"
                language: "western"
                pattern: "<your_own_value>"
                pattern-type: "wildcard"
                score: "10"
                status: "enable"
                where: "subject"
            id:  "13"
            name: "default_name_14"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/spamfilter/fortios_spamfilter_bword_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure AntiSpam banned word list.
        fortios_spamfilter_bword:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          spamfilter_bword:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "spam"
                id:  "6"
                language: "western"
                pattern: "<your_own_value>"
                pattern-type: "wildcard"
                score: "10"
                status: "enable"
                where: "subject"
            id:  "13"
            name: "default_name_14"




