=======================
fortios_log_eventfilter
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
      - name: Configure log event filters.
        fortios_log_eventfilter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log_eventfilter:
            compliance-check: "enable"
            endpoint: "enable"
            event: "enable"
            ha: "enable"
            router: "enable"
            security-rating: "enable"
            system: "enable"
            user: "enable"
            vpn: "enable"
            wan-opt: "enable"
            wireless-activity: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log/fortios_log_eventfilter_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure log event filters.
        fortios_log_eventfilter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log_eventfilter:
            compliance-check: "enable"
            endpoint: "enable"
            event: "enable"
            ha: "enable"
            router: "enable"
            security-rating: "enable"
            system: "enable"
            user: "enable"
            vpn: "enable"
            wan-opt: "enable"
            wireless-activity: "enable"




