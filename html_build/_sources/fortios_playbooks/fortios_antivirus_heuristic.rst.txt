===========================
fortios_antivirus_heuristic
===========================


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
      - name: Configure global heuristic options.
        fortios_antivirus_heuristic:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          antivirus_heuristic:
            mode: "pass"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

