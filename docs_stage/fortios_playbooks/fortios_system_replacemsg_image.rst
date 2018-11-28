===============================
fortios_system_replacemsg_image
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
      - name: Configure replacement message images.
        fortios_system_replacemsg_image:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_replacemsg_image:
            state: "present"
            image-base64: "<your_own_value>"
            image-type: "gif"
            name: "default_name_5"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_replacemsg_image_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure replacement message images.
        fortios_system_replacemsg_image:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_replacemsg_image:
            state: "present"
            image-base64: "<your_own_value>"
            image-type: "gif"
            name: "default_name_5"




