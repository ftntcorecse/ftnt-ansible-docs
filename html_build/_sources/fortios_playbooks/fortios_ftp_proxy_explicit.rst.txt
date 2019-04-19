==========================
fortios_ftp_proxy_explicit
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
      - name: Configure explicit FTP proxy settings.
        fortios_ftp_proxy_explicit:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ftp_proxy_explicit:
            incoming-ip: "<your_own_value>"
            incoming-port: "<your_own_value>"
            outgoing-ip: "<your_own_value>"
            sec-default-action: "accept"
            status: "enable"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/ftp_proxy/fortios_ftp_proxy_explicit_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure explicit FTP proxy settings.
        fortios_ftp_proxy_explicit:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          ftp_proxy_explicit:
            incoming-ip: "<your_own_value>"
            incoming-port: "<your_own_value>"
            outgoing-ip: "<your_own_value>"
            sec-default-action: "accept"
            status: "enable"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

