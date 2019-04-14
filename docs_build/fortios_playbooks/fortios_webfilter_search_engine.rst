===============================
fortios_webfilter_search_engine
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
      - name: Configure web filter search engines.
        fortios_webfilter_search_engine:
<<<<<<< Updated upstream
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
=======
          host:  "{{  host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{  vdom }}"
>>>>>>> Stashed changes
          webfilter_search_engine:
            state: "present"
            charset: "utf-8"
            hostname: "myhostname"
            name: "default_name_5"
            query: "<your_own_value>"
            safesearch: "disable"
            safesearch-str: "<your_own_value>"
<<<<<<< Updated upstream
            url: "myurl.com"
=======
            url: "http://myurl.com"
>>>>>>> Stashed changes



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/webfilter/fortios_webfilter_search_engine_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure web filter search engines.
        fortios_webfilter_search_engine:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          webfilter_search_engine:
            state: "present"
            charset: "utf-8"
            hostname: "myhostname"
            name: "default_name_5"
            query: "<your_own_value>"
            safesearch: "disable"
            safesearch-str: "<your_own_value>"
            url: "myurl.com"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

