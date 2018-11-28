==============================
fortios_switch_controller_vlan
==============================


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
      - name: Configure VLANs for switch controller.
        fortios_switch_controller_vlan:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_vlan:
            state: "present"
            auth: "radius"
            color: "4"
            comments: "<your_own_value>"
            name: "default_name_6"
            portal-message-override-group: "<your_own_value>"
            portal-message-overrides:
                auth-disclaimer-page: "<your_own_value>"
                auth-login-failed-page: "<your_own_value>"
                auth-login-page: "<your_own_value>"
                auth-reject-page: "<your_own_value>"
            radius-server: "<your_own_value> (source user.radius.name)"
            security: "open"
            selected-usergroups:
             -
                name: "default_name_16 (source user.group.name)"
            usergroup: "<your_own_value> (source user.group.name)"
            vdom: "<your_own_value>"
            vlanid: "19"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller/fortios_switch_controller_vlan_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure VLANs for switch controller.
        fortios_switch_controller_vlan:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller_vlan:
            state: "present"
            auth: "radius"
            color: "4"
            comments: "<your_own_value>"
            name: "default_name_6"
            portal-message-override-group: "<your_own_value>"
            portal-message-overrides:
                auth-disclaimer-page: "<your_own_value>"
                auth-login-failed-page: "<your_own_value>"
                auth-login-page: "<your_own_value>"
                auth-reject-page: "<your_own_value>"
            radius-server: "<your_own_value> (source user.radius.name)"
            security: "open"
            selected-usergroups:
             -
                name: "default_name_16 (source user.group.name)"
            usergroup: "<your_own_value> (source user.group.name)"
            vdom: "<your_own_value>"
            vlanid: "19"




