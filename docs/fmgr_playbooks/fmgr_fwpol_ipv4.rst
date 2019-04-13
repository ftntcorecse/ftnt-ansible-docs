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
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
        fmgr_fwpol_ipv4:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
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
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
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
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
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

fmgr_fwpol_ipv4_delete_basic.yml
++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FW POLICIES
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NO NAT (WIDE OPEN)
        fmgr_fwpol_ipv4:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy"
    
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES
        fmgr_fwpol_ipv4:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy_2"
    
      - name: ADD VERY BASIC IPV4 POLICY WITH NAT AND MULTIPLE ENTRIES
        fmgr_fwpol_ipv4:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          package_name: "default"
          name: "Basic_IPv4_Policy_3"




