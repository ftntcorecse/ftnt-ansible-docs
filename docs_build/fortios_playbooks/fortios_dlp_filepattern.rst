=======================
fortios_dlp_filepattern
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
      - name: Configure file patterns used by DLP blocking.
        fortios_dlp_filepattern:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          dlp_filepattern:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                file-type: "7z"
                filter-type: "pattern"
                pattern: "<your_own_value>"
            id:  "8"
            name: "default_name_9"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/dlp/fortios_dlp_filepattern_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure file patterns used by DLP blocking.
        fortios_dlp_filepattern:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          dlp_filepattern:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                file-type: "7z"
                filter-type: "pattern"
                pattern: "<your_own_value>"
            id:  "8"
            name: "default_name_9"




