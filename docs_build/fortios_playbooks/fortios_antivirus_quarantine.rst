============================
fortios_antivirus_quarantine
============================


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
      - name: Configure quarantine options.
        fortios_antivirus_quarantine:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          antivirus_quarantine:
            agelimit: "3"
            destination: "NULL"
            drop-blocked: "imap"
            drop-heuristic: "imap"
            drop-infected: "imap"
            lowspace: "drop-new"
            maxfilesize: "9"
            quarantine-quota: "10"
            store-blocked: "imap"
            store-heuristic: "imap"
            store-infected: "imap"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

