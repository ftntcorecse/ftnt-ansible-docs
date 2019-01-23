===================
fortios_ipv4_policy
===================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: Allow external DNS call
      fortios_ipv4_policy:
        host: 192.168.0.254
        username: admin
        password: password
        id: 42
        src_addr: internal_network
        dst_addr: all
        service: dns
        nat: True
        state: present
        policy_action: accept
        logtraffic: disable
    
    - name: Public Web
      fortios_ipv4_policy:
        host: 192.168.0.254
        username: admin
        password: password
        id: 42
        src_addr: all
        dst_addr: webservers
        services:
          - http
          - https
        state: present
        policy_action: accept
    
    - name: Some Policy
      fortios_ipv4_policy:
        host: 192.168.0.254
        username: admin
        password: password
        id: 42
        comment: "no comment (created by ansible)"
        src_intf: vl1000
        src_addr:
          - some_serverA
          - some_serverB
        dst_intf:
          - vl2000
          - vl3000
        dst_addr: all
        services:
          - HTTP
          - HTTPS
        nat: True
        state: present
        policy_action: accept
        logtraffic: disable
      tags:
        - policy



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

