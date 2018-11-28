===============================
fortios_dnsfilter_domain_filter
===============================


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
      - name: Configure DNS domain filters.
        fortios_dnsfilter_domain_filter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          dnsfilter_domain_filter:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "block"
                domain: "<your_own_value>"
                id:  "7"
                status: "enable"
                type: "simple"
            id:  "10"
            name: "default_name_11"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/dnsfilter/fortios_dnsfilter_domain_filter_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure DNS domain filters.
        fortios_dnsfilter_domain_filter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          dnsfilter_domain_filter:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "block"
                domain: "<your_own_value>"
                id:  "7"
                status: "enable"
                type: "simple"
            id:  "10"
            name: "default_name_11"




