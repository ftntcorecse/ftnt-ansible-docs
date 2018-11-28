======================================
fortios_web_proxy_forward_server_group
======================================


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
      - name: Configure a forward server group consisting or multiple forward servers. Supports failover and load balancing.
        fortios_web_proxy_forward_server_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          web_proxy_forward_server_group:
            state: "present"
            affinity: "enable"
            group-down-option: "block"
            ldb-method: "weighted"
            name: "default_name_6"
            server-list:
             -
                name: "default_name_8 (source web-proxy.forward-server.name)"
                weight: "9"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/web_proxy/fortios_web_proxy_forward_server_group_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure a forward server group consisting or multiple forward servers. Supports failover and load balancing.
        fortios_web_proxy_forward_server_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          web_proxy_forward_server_group:
            state: "present"
            affinity: "enable"
            group-down-option: "block"
            ldb-method: "weighted"
            name: "default_name_6"
            server-list:
             -
                name: "default_name_8 (source web-proxy.forward-server.name)"
                weight: "9"




