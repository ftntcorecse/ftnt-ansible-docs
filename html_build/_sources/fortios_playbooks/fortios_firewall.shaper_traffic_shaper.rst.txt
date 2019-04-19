======================================
fortios_firewall.shaper_traffic_shaper
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
      - name: Configure shared traffic shaper.
        fortios_firewall.shaper_traffic_shaper:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.shaper_traffic_shaper:
            state: "present"
            bandwidth-unit: "kbps"
            diffserv: "enable"
            diffservcode: "<your_own_value>"
            guaranteed-bandwidth: "6"
            maximum-bandwidth: "7"
            name: "default_name_8"
            per-policy: "disable"
            priority: "low"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.shaper/fortios_firewall.shaper_traffic_shaper_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure shared traffic shaper.
        fortios_firewall.shaper_traffic_shaper:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.shaper_traffic_shaper:
            state: "present"
            bandwidth-unit: "kbps"
            diffserv: "enable"
            diffservcode: "<your_own_value>"
            guaranteed-bandwidth: "6"
            maximum-bandwidth: "7"
            name: "default_name_8"
            per-policy: "disable"
            priority: "low"




