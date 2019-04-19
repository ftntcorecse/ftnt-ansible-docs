===========================
fortios_system_auto_install
===========================


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
      - name: Configure USB auto installation.
        fortios_system_auto_install:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_auto_install:
            auto-install-config: "enable"
            auto-install-image: "enable"
            default-config-file: "<your_own_value>"
            default-image-file: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_auto_install_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure USB auto installation.
        fortios_system_auto_install:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_auto_install:
            auto-install-config: "enable"
            auto-install-image: "enable"
            default-config-file: "<your_own_value>"
            default-image-file: "<your_own_value>"




