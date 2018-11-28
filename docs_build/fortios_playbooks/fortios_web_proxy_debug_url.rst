===========================
fortios_web_proxy_debug_url
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
      - name: Configure debug URL addresses.
        fortios_web_proxy_debug_url:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          web_proxy_debug_url:
            state: "present"
            exact: "enable"
            name: "default_name_4"
            status: "enable"
            url-pattern: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/web_proxy/fortios_web_proxy_debug_url_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure debug URL addresses.
        fortios_web_proxy_debug_url:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          web_proxy_debug_url:
            state: "present"
            exact: "enable"
            name: "default_name_4"
            status: "enable"
            url-pattern: "<your_own_value>"




