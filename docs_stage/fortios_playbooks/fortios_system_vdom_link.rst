========================
fortios_system_vdom_link
========================


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
      - name: Configure VDOM links.
        fortios_system_vdom_link:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_link:
            state: "present"
            name: "default_name_3"
            type: "ppp"
            vcluster: "vcluster1"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vdom_link_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure VDOM links.
        fortios_system_vdom_link:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_link:
            state: "present"
            name: "default_name_3"
            type: "ppp"
            vcluster: "vcluster1"




