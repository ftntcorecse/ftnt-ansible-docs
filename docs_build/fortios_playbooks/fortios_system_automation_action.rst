================================
fortios_system_automation_action
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
      - name: Action for automation stitches.
        fortios_system_automation_action:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_action:
            state: "present"
            action-type: "email"
            aws-api-id: "<your_own_value>"
            aws-api-key: "<your_own_value>"
            aws-api-path: "<your_own_value>"
            aws-api-stage: "<your_own_value>"
            aws-region: "<your_own_value>"
            delay: "9"
            email-subject: "<your_own_value>"
            email-to:
             -
                name: "default_name_12"
            headers:
             -
                header: "<your_own_value>"
            http-body: "<your_own_value>"
            method: "post"
            minimum-interval: "17"
            name: "default_name_18"
            port: "19"
            protocol: "http"
            required: "enable"
            uri: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_automation_action_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Action for automation stitches.
        fortios_system_automation_action:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_automation_action:
            state: "present"
            action-type: "email"
            aws-api-id: "<your_own_value>"
            aws-api-key: "<your_own_value>"
            aws-api-path: "<your_own_value>"
            aws-api-stage: "<your_own_value>"
            aws-region: "<your_own_value>"
            delay: "9"
            email-subject: "<your_own_value>"
            email-to:
             -
                name: "default_name_12"
            headers:
             -
                header: "<your_own_value>"
            http-body: "<your_own_value>"
            method: "post"
            minimum-interval: "17"
            name: "default_name_18"
            port: "19"
            protocol: "http"
            required: "enable"
            uri: "<your_own_value>"




