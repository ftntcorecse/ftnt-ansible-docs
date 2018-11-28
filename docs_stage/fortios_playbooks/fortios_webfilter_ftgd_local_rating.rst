===================================
fortios_webfilter_ftgd_local_rating
===================================


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
      - name: Configure local FortiGuard Web Filter local ratings.
        fortios_webfilter_ftgd_local_rating:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_ftgd_local_rating:
            state: "present"
            rating: "<your_own_value>"
            status: "enable"
            url: "myurl.com"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/webfilter/fortios_webfilter_ftgd_local_rating_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure local FortiGuard Web Filter local ratings.
        fortios_webfilter_ftgd_local_rating:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_ftgd_local_rating:
            state: "present"
            rating: "<your_own_value>"
            status: "enable"
            url: "myurl.com"




