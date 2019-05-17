===============
fmgr_fwpol_ipv4
===============


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
      fmgr_fwpol_ipv4:
        mode: "set"
        adom: "ansible"
        package_name: "default"
        name: "Basic_IPv4_Policy"
        comments: "Created by Ansible"
        action: "accept"
        dstaddr: "all"
        srcaddr: "all"
        dstintf: "any"
        srcintf: "any"
        logtraffic: "utm"
        service: "ALL"
        schedule: "always"
    
    - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES
      fmgr_fwpol_ipv4:
        mode: "set"
        adom: "ansible"
        package_name: "default"
        name: "Basic_IPv4_Policy_2"
        comments: "Created by Ansible"
        action: "accept"
        dstaddr: "google-play"
        srcaddr: "all"
        dstintf: "any"
        srcintf: "any"
        logtraffic: "utm"
        service: "HTTP, HTTPS"
        schedule: "always"
        nat: "enable"
        users: "karen, kevin"
    
    - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES AND SEC PROFILES
      fmgr_fwpol_ipv4:
        mode: "set"
        adom: "ansible"
        package_name: "default"
        name: "Basic_IPv4_Policy_3"
        comments: "Created by Ansible"
        action: "accept"
        dstaddr: "google-play, autoupdate.opera.com"
        srcaddr: "corp_internal"
        dstintf: "zone_wan1, zone_wan2"
        srcintf: "zone_int1"
        logtraffic: "utm"
        service: "HTTP, HTTPS"
        schedule: "always"
        nat: "enable"
        users: "karen, kevin"
        av_profile: "sniffer-profile"
        ips_sensor: "default"
    



Playbook File Examples
----------------------


fmgr_fwpol_ipv4_add_basic.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICIES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
        fmgr_fwpol_ipv4:
          mode: "set"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy"
          comments: "Created by Ansible"
          action: "accept"
          dstaddr: "all"
          srcaddr: "all"
          dstintf: "any"
          srcintf: "any"
          logtraffic: "utm"
          service: "ALL"
          schedule: "always"
        ignore_errors: yes
        ignore_unreachable: yes
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES
        fmgr_fwpol_ipv4:
          mode: "set"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy_2"
          comments: "Created by Ansible"
          action: "accept"
          dstaddr: "google-play"
          srcaddr: "all"
          dstintf: "any"
          srcintf: "any"
          logtraffic: "utm"
          service: "HTTP, HTTPS"
          schedule: "always"
          nat: "enable"
          #users: "karen, kevin"
        ignore_errors: yes
        ignore_unreachable: yes
    
    #  - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES AND SEC PROFILES
    #    fmgr_fwpol_ipv4:
    #      mode: "set"
    #      adom: "ansible"
    #      package_name: "default"
    #      name: "Basic_IPv4_Policy_3"
    #      comments: "Created by Ansible"
    #      action: "accept"
    #      dstaddr: "google-play, autoupdate.opera.com"
    #      srcaddr: "any"
    #      dstintf: "zone_wan1, zone_wan2"
    #      srcintf: "zone_int1"
    #      logtraffic: "utm"
    #      service: "HTTP, HTTPS"
    #      schedule: "always"
    #      nat: "enable"
    #      #users: "karen, kevin"
    #      av_profile: "sniffer-profile"
    #      ips_sensor: "default"
    #    ignore_errors: yes
    #    ignore_unreachable: yes

fmgr_fwpol_ipv4_run_all.sh
++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_fwpol_ipv4_add_basic.yml -vvvv
    ansible-playbook fmgr_fwpol_ipv4_delete_basic.yml -vvvv


fmgr_fwpol_ipv4_add_fsso.yml
++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICIES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD VERY BASIC IPV4 POLICY WITH FSSO
        fmgr_fwpol_ipv4:
          mode: "set"
          adom: "root"
          package_name: "default"
          name: "Test_FSSO_IPv4_Policy"
          comments: "Created by Ansible"
          action: "accept"
          dstaddr: "srcaddr2"
          srcaddr: "srcaddr1"
          dstintf: "wan1"
          srcintf: "lan"
          logtraffic: "all"
          service: "ALL"
          schedule: "always"
          fsso: "enable"
          groups: "SSL_OMG_GR"


fmgr_fwpol_ipv4_delete_basic.yml
++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FW POLICIES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
        fmgr_fwpol_ipv4:
          mode: "delete"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy"
    
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES
        fmgr_fwpol_ipv4:
          mode: "delete"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy_2"
    
    #  - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES
    #    fmgr_fwpol_ipv4:
    #      mode: "delete"
    #      adom: "ansible"
    #      package_name: "default"
    #      name: "Basic_IPv4_Policy_3"




