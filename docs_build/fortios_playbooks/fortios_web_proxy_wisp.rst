======================
fortios_web_proxy_wisp
======================


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
      - name: Configure Wireless Internet service provider (WISP) servers.
        fortios_web_proxy_wisp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          web_proxy_wisp:
            state: "present"
            comment: "Comment."
            max-connections: "4"
            name: "default_name_5"
            outgoing-ip: "<your_own_value>"
            server-ip: "<your_own_value>"
            server-port: "8"
            timeout: "9"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/web_proxy/fortios_web_proxy_wisp_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure Wireless Internet service provider (WISP) servers.
        fortios_web_proxy_wisp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          web_proxy_wisp:
            state: "present"
            comment: "Comment."
            max-connections: "4"
            name: "default_name_5"
            outgoing-ip: "<your_own_value>"
            server-ip: "<your_own_value>"
            server-port: "8"
            timeout: "9"




