==================
fmgr_fwobj_address
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: ADD IPv4 IP ADDRESS OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "ipmask"
        ipv4addr: "10.7.220.30/32"
        name: "ansible_v4Obj"
        comment: "Created by Ansible"
        color: "6"
    
    - name: ADD IPv4 IP ADDRESS OBJECT MORE OPTIONS
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "ipmask"
        ipv4addr: "10.7.220.34/32"
        name: "ansible_v4Obj_MORE"
        comment: "Created by Ansible"
        color: "6"
        allow_routing: "enable"
        cache_ttl: "180"
        associated_interface: "port1"
        obj_id: "123"
    
    - name: ADD IPv4 IP ADDRESS SUBNET OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "ipmask"
        ipv4addr: "10.7.220.0/255.255.255.128"
        name: "ansible_subnet"
        comment: "Created by Ansible"
        mode: "set"
    
    - name: ADD IPv4 IP ADDRESS RANGE OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "iprange"
        start_ip: "10.7.220.1"
        end_ip: "10.7.220.125"
        name: "ansible_range"
        comment: "Created by Ansible"
    
    - name: ADD IPv4 IP ADDRESS WILDCARD OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "wildcard"
        wildcard: "10.7.220.30/255.255.255.255"
        name: "ansible_wildcard"
        comment: "Created by Ansible"
    
    - name: ADD IPv4 IP ADDRESS WILDCARD FQDN OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "wildcard-fqdn"
        wildcard_fqdn: "*.myds.com"
        name: "Synology myds DDNS service"
        comment: "Created by Ansible"
    
    - name: ADD IPv4 IP ADDRESS FQDN OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "fqdn"
        fqdn: "ansible.com"
        name: "ansible_fqdn"
        comment: "Created by Ansible"
    
    - name: ADD IPv4 IP ADDRESS GEO OBJECT
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "geography"
        country: "usa"
        name: "ansible_geo"
        comment: "Created by Ansible"
    
    - name: ADD IPv6 ADDRESS
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv6: "ipprefix"
        ipv6addr: "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
        name: "ansible_v6Obj"
        comment: "Created by Ansible"
    
    - name: ADD IPv6 ADDRESS RANGE
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv6: "iprange"
        start_ip: "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
        end_ip: "2001:0db8:85a3:0000:0000:8a2e:0370:7446"
        name: "ansible_v6range"
        comment: "Created by Ansible"
    
    - name: ADD IPv4 IP ADDRESS GROUP
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv4: "group"
        group_name: "ansibleIPv4Group"
        group_members: "ansible_fqdn, ansible_wildcard, ansible_range"
    
    - name: ADD IPv6 IP ADDRESS GROUP
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ipv6: "group"
        group_name: "ansibleIPv6Group"
        group_members: "ansible_v6Obj, ansible_v6range"
    
    - name: ADD MULTICAST RANGE
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        multicast: "multicastrange"
        start_ip: "224.0.0.251"
        end_ip: "224.0.0.251"
        name: "ansible_multicastrange"
        comment: "Created by Ansible"
    
    - name: ADD BROADCAST SUBNET
      fmgr_fwobj_address:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        multicast: "broadcastmask"
        ipv4addr: "10.7.220.0/24"
        name: "ansible_broadcastSubnet"
        comment: "Created by Ansible"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

