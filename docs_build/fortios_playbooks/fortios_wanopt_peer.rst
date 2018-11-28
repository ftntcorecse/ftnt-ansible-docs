===================
fortios_wanopt_peer
===================


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
      - name: Configure WAN optimization peers.
        fortios_wanopt_peer:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wanopt_peer:
            state: "present"
            ip: "<your_own_value>"
            peer-host-id: "myhostname"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wanopt/fortios_wanopt_peer_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure WAN optimization peers.
        fortios_wanopt_peer:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wanopt_peer:
            state: "present"
            ip: "<your_own_value>"
            peer-host-id: "myhostname"




