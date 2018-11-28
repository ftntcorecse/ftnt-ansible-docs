=================================
fortios_system_ips_urlfilter_dns6
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
      - name: Configure IPS URL filter IPv6 DNS servers.
        fortios_system_ips_urlfilter_dns6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ips_urlfilter_dns6:
            state: "present"
            address6: "<your_own_value>"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_ips_urlfilter_dns6_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS URL filter IPv6 DNS servers.
        fortios_system_ips_urlfilter_dns6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ips_urlfilter_dns6:
            state: "present"
            address6: "<your_own_value>"
            status: "enable"




