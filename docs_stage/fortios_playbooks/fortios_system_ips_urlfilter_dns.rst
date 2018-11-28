================================
fortios_system_ips_urlfilter_dns
================================


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
      - name: Configure IPS URL filter DNS servers.
        fortios_system_ips_urlfilter_dns:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ips_urlfilter_dns:
            state: "present"
            address: "<your_own_value>"
            ipv6-capability: "enable"
            status: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_ips_urlfilter_dns_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS URL filter DNS servers.
        fortios_system_ips_urlfilter_dns:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ips_urlfilter_dns:
            state: "present"
            address: "<your_own_value>"
            ipv6-capability: "enable"
            status: "enable"




