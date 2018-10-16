==================
fmgr_fwobj_address
==================

Not Parsed


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


fmgr_fwobj_ipv4_add_fqdn.yml
++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS FQDN OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "fqdn"
          mode: "add"
          adom: "ansible"
          fqdn: "bluesnews.com"
          name: "Bluesnews"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"


fmgr_fwobj_ipv4_add_geo.yml
+++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS GEO OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "geography"
          country: "US"
          mode: "add"
          adom: "ansible"
          name: "ansible_geo"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ipv4, test123, test321"

fmgr_fwobj_ipv4_add_ipmask.yml
++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG IPv4 IP ADDRESS OBJECT
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "ipmask"
          ipv4addr: "10.7.220.30/32"
          name: "ansible_v4Obj_ipMask2"
          comment: "Ansible is fun! Paramgram!"
          tags: "ansible, ipv4, object"
          color: "26"
    
      - name: ADD IPv4 IP ADDRESS OBJECT MORE OPTIONS
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "ipmask"
          ipv4addr: "10.7.220.41/32"
          name: "ansible_v4Obj_MORE"
          comment: "Ansible more options"
          tags: "ansible, ipv4, object"
          color: "6"
          allow_routing: "enable"
          cache_ttl: "180"
          associated_interface: "port1"
          adom: "ansible"
          mode: "set"


fmgr_fwobj_ipv4_add_iprange.yml
+++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS RANGE OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          ipv4: "iprange"
          start_ip: "10.7.220.1"
          end_ip: "10.7.220.50"
          name: "ansible_v4Obj_Range"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"
    
      - name: ADD IPv4 IP ADDRESS RANGE OBJECT 2
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "ansible"
          ipv4: "iprange"
          start_ip: "10.7.220.100"
          end_ip: "10.7.220.150"
          name: "ansible_v4Obj_Range2"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"

fmgr_fwobj_ipv4_add_ipsubnet.yml
++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          ipv4: "ipmask"
          ipv4addr: "10.7.220.0/25"
          name: "ansible_v4Obj_Subnet1"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"
    
      - name: ADD IPv4 IP ADDRESS OBJECT (NON CIDR TEST)
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          ipv4: "ipmask"
          ipv4addr: "10.7.220.128/255.255.255.128"
          name: "ansible_v4Obj_Subnet2"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"


fmgr_fwobj_ipv4_add_wildcard.yml
++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS WILDCARD OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          ipv4: "wildcard"
          wildcard: "10.7.220.0/24"
          name: "ansible_v4Obj_wildCard"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"


fmgr_fwobj_ipv4_add_wildcard_fqdn.yml
+++++++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS WILDCARD FQDN OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "wildcard-fqdn"
          mode: "add"
          adom: "ansible"
          wildcard_fqdn: "*.myds.com"
          name: "Synology myds DDNS service"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"


fmgr_fwobj_ipv4_add_z_group.yml
+++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv4 IP ADDRESS GROUP
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "add"
          ipv4: "group"
          group_name: "ansibleIPv4Group"
          group_members: "Bluesnews, ansible_v4Obj_Range"
          color: "22"


fmgr_fwobj_ipv4_broadcast_subnet.yml
++++++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG IPv4 IP ADDRESS OBJECT
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD BROADCAST SUBNET
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "add"
          multicast: "broadcastmask"
          ipv4addr: "10.7.220.0/24"
          name: "ansible_broadcastSubnet"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"


fmgr_fwobj_ipv4_del_all.yml
+++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: DELETE IPv4 IP ADDRESS GROUP
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "delete"
          ipv4: "group"
          group_name: "ansibleIPv4Group"
    
      - name: DELETE IPv4 IP ADDRESS RANGE OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "iprange"
          name: "ansible_v4Obj_Range"
    
      - name: DELETE IPv4 IP ADDRESS RANGE OBJECT 3
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "iprange"
          name: "ansible_v4Obj_MORE"
    
      - name: DELETE IPv4 IP ADDRESS RANGE OBJECT 4
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "iprange"
          name: "ansible_v4Obj_ipMask2"
    
      - name: DELETE IPv4 IP ADDRESS RANGE OBJECT 2
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "iprange"
          name: "ansible_v4Obj_Range2"
    
      - name: DELETE IPv4 IP ADDRESS OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "ipmask"
          name: "ansible_v4Obj_ipMask"
    
      - name: DELETE IPv4 IP ADDRESS OBJECT (NON CIDR TEST)
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "ipmask"
          name: "ansible_v4Obj_Subnet2"
    
      - name: DELETE IPv4 IP ADDRESS OBJECT (NON CIDR TEST) 2
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "ipmask"
          name: "ansible_v4Obj_Subnet1"
    
      - name: DELETE IPv4 IP ADDRESS WILDCARD OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv4: "wildcard"
          name: "ansible_v4Obj_wildCard"
    
      - name: DELETE IPv4 IP ADDRESS WILDCARD FQDN OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "wildcard-fqdn"
          mode: "delete"
          adom: "ansible"
          name: "Synology myds DDNS service"
    
      - name: DELETE IPv4 IP ADDRESS FQDN OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "fqdn"
          mode: "delete"
          adom: "ansible"
          name: "Bluesnews"
    
      - name: DELETE IPv4 IP ADDRESS GEO OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ipv4: "geography"
          mode: "delete"
          adom: "ansible"
          name: "ansible_geo"
    
      - name: DELETE IPv6 IP ADDRESS GROUP
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "delete"
          ipv6: "group"
          group_name: "ansibleIPv6Group"
    
      - name: DELETE IPv6 IP ADDRESS RANGE OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "delete"
          adom: "ansible"
          ipv6: "iprange"
          name: "ansible_v6Obj_Range"
    
      - name: DELETE IPv6 ADDRESS
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "delete"
          ipv6: "ip"
          name: "ansible_v6Obj"
    
      - name: DELETE BROADCAST SUBNET
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          multicast: "broadcastmask"
          mode: "delete"
          name: "ansible_broadcastSubnet"
    
      - name: DELETE MULTICAST RANGE
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "delete"
          multicast: "multicastrange"
          name: "ansible_multicastrange"

fmgr_fwobj_ipv4_multicast_range.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG IPv4 IP ADDRESS OBJECT
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD MULTICAST RANGE
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "add"
          multicast: "multicastrange"
          start_ip: "224.0.0.251"
          end_ip: "224.0.0.251"
          name: "ansible_multicastrange"
          comment: "Dev by Ansible"
          color: "22"
          tags: "blahBlahBlah"


fmgr_fwobj_ipv6_add_ip.yml
++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv6 ADDRESS
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "add"
          ipv6: "ip"
          ipv6addr: "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
          name: "ansible_v6Obj"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"


fmgr_fwobj_ipv6_add_iprange.yml
+++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv6 IP ADDRESS RANGE OBJECT
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "add"
          adom: "ansible"
          ipv6: "iprange"
          start_ip: "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
          end_ip: "2001:0db8:85a3:0000:0000:8a2e:0370:7446"
          name: "ansible_v6Obj_Range"
          comment: "Dev Example for Ansible"
          color: "22"
          tags: "ansible, ipv4, test123, test321"

fmgr_fwobj_ipv6_add_z_group.yml
+++++++++++++++++++++++++++++++

.. code-block:: yaml


    
    - name: CONFIG FMGR FIREWALL OBJECTS
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
      - name: ADD IPv6 IP ADDRESS GROUP
        fmgr_fwobj_address:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          adom: "ansible"
          mode: "add"
          ipv6: "group"
          group_name: "ansibleIPv6Group"
          group_members: "ansible_v6Obj_Range, ansible_v6Obj"
          color: "22"
          tags: "ansible, ipv4, test123, test321"
          comment: "test123 comment"




