========================================
fortios_webfilter_ips_urlfilter_setting6
========================================


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
      - name: Configure IPS URL filter settings for IPv6.
        fortios_webfilter_ips_urlfilter_setting6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_ips_urlfilter_setting6:
            device: "<your_own_value> (source system.interface.name)"
            distance: "4"
            gateway6: "<your_own_value>"
            geo-filter: "<your_own_value>"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/webfilter/fortios_webfilter_ips_urlfilter_setting6_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPS URL filter settings for IPv6.
        fortios_webfilter_ips_urlfilter_setting6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_ips_urlfilter_setting6:
            device: "<your_own_value> (source system.interface.name)"
            distance: "4"
            gateway6: "<your_own_value>"
            geo-filter: "<your_own_value>"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

