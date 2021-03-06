============================================
fortios_wanopt_content_delivery_network_rule
============================================


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
      - name: Configure WAN optimization content delivery network rules.
        fortios_wanopt_content_delivery_network_rule:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wanopt_content_delivery_network_rule:
            state: "present"
            category: "vcache"
            comment: "Comment about this CDN-rule."
            host-domain-name-suffix:
             -
                name: "default_name_6"
            name: "default_name_7"
            request-cache-control: "enable"
            response-cache-control: "enable"
            response-expires: "enable"
            rules:
             -
                content-id:
                    end-direction: "forward"
                    end-skip: "14"
                    end-str: "<your_own_value>"
                    range-str: "<your_own_value>"
                    start-direction: "forward"
                    start-skip: "18"
                    start-str: "<your_own_value>"
                    target: "path"
                match-entries:
                 -
                    id:  "22"
                    pattern:
                     -
                        string: "<your_own_value>"
                    target: "path"
                match-mode: "all"
                name: "default_name_27"
                skip-entries:
                 -
                    id:  "29"
                    pattern:
                     -
                        string: "<your_own_value>"
                    target: "path"
                skip-rule-mode: "all"
            status: "enable"
            text-response-vcache: "enable"
            updateserver: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wanopt/fortios_wanopt_content_delivery_network_rule_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure WAN optimization content delivery network rules.
        fortios_wanopt_content_delivery_network_rule:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wanopt_content_delivery_network_rule:
            state: "present"
            category: "vcache"
            comment: "Comment about this CDN-rule."
            host-domain-name-suffix:
             -
                name: "default_name_6"
            name: "default_name_7"
            request-cache-control: "enable"
            response-cache-control: "enable"
            response-expires: "enable"
            rules:
             -
                content-id:
                    end-direction: "forward"
                    end-skip: "14"
                    end-str: "<your_own_value>"
                    range-str: "<your_own_value>"
                    start-direction: "forward"
                    start-skip: "18"
                    start-str: "<your_own_value>"
                    target: "path"
                match-entries:
                 -
                    id:  "22"
                    pattern:
                     -
                        string: "<your_own_value>"
                    target: "path"
                match-mode: "all"
                name: "default_name_27"
                skip-entries:
                 -
                    id:  "29"
                    pattern:
                     -
                        string: "<your_own_value>"
                    target: "path"
                skip-rule-mode: "all"
            status: "enable"
            text-response-vcache: "enable"
            updateserver: "enable"




