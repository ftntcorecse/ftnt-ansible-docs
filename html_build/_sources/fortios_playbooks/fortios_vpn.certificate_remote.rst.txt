==============================
fortios_vpn.certificate_remote
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
      - name: Remote certificate as a PEM file.
        fortios_vpn.certificate_remote:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.certificate_remote:
            state: "present"
            name: "default_name_3"
            range: "global"
            remote: "<your_own_value>"
            source: "factory"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.certificate/fortios_vpn.certificate_remote_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Remote certificate as a PEM file.
        fortios_vpn.certificate_remote:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.certificate_remote:
            state: "present"
            name: "default_name_3"
            range: "global"
            remote: "<your_own_value>"
            source: "factory"




