=================================
fortios_vpn.ssl.web_user_bookmark
=================================


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
      - name: Configure SSL VPN user bookmark.
        fortios_vpn.ssl.web_user_bookmark:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ssl.web_user_bookmark:
            state: "present"
            bookmarks:
             -
                additional-params: "<your_own_value>"
                apptype: "citrix"
                description: "<your_own_value>"
                folder: "<your_own_value>"
                form-data:
                 -
                    name: "default_name_9"
                    value: "<your_own_value>"
                host: "<your_own_value>"
                listening-port: "12"
                load-balancing-info: "<your_own_value>"
                logon-password: "<your_own_value>"
                logon-user: "<your_own_value>"
                name: "default_name_16"
                port: "17"
                preconnection-blob: "<your_own_value>"
                preconnection-id: "19"
                remote-port: "20"
                security: "rdp"
                server-layout: "de-de-qwertz"
                show-status-window: "enable"
                sso: "disable"
                sso-credential: "sslvpn-login"
                sso-credential-sent-once: "enable"
                sso-password: "<your_own_value>"
                sso-username: "<your_own_value>"
                url: "myurl.com"
            custom-lang: "<your_own_value> (source system.custom-language.name)"
            name: "default_name_31"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.ssl.web/fortios_vpn.ssl.web_user_bookmark_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure SSL VPN user bookmark.
        fortios_vpn.ssl.web_user_bookmark:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ssl.web_user_bookmark:
            state: "present"
            bookmarks:
             -
                additional-params: "<your_own_value>"
                apptype: "citrix"
                description: "<your_own_value>"
                folder: "<your_own_value>"
                form-data:
                 -
                    name: "default_name_9"
                    value: "<your_own_value>"
                host: "<your_own_value>"
                listening-port: "12"
                load-balancing-info: "<your_own_value>"
                logon-password: "<your_own_value>"
                logon-user: "<your_own_value>"
                name: "default_name_16"
                port: "17"
                preconnection-blob: "<your_own_value>"
                preconnection-id: "19"
                remote-port: "20"
                security: "rdp"
                server-layout: "de-de-qwertz"
                show-status-window: "enable"
                sso: "disable"
                sso-credential: "sslvpn-login"
                sso-credential-sent-once: "enable"
                sso-password: "<your_own_value>"
                sso-username: "<your_own_value>"
                url: "myurl.com"
            custom-lang: "<your_own_value> (source system.custom-language.name)"
            name: "default_name_31"




