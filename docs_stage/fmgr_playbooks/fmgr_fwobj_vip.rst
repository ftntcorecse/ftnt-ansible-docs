==============
fmgr_fwobj_vip
==============


Playbook Task Examples
----------------------

.. code-block:: yaml

    # BASIC FULL STATIC NAT MAPPING
    - name: EDIT FMGR_FIREWALL_VIP SNAT
      fmgr_fwobj_vip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        name: "Basic StaticNAT Map"
        mode: "set"
        adom: "ansible"
        type: "static-nat"
        extip: "82.72.192.185"
        extintf: "any"
        mappedip: "10.7.220.25"
        comment: "Created by Ansible"
        color: "17"
    
    # BASIC PORT PNAT MAPPING
    - name: EDIT FMGR_FIREWALL_VIP PNAT
      fmgr_fwobj_vip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        name: "Basic PNAT Map Port 10443"
        mode: "set"
        adom: "ansible"
        type: "static-nat"
        extip: "82.72.192.185"
        extport: "10443"
        extintf: "any"
        portforward: "enable"
        protocol: "tcp"
        mappedip: "10.7.220.25"
        mappedport: "443"
        comment: "Created by Ansible"
        color: "17"
    
    # BASIC DNS TRANSLATION NAT
    - name: EDIT FMGR_FIREWALL_DNST
      fmgr_fwobj_vip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        name: "Basic DNS Translation"
        mode: "set"
        adom: "ansible"
        type: "dns-translation"
        extip: "192.168.0.1-192.168.0.100"
        extintf: "dmz"
        mappedip: "3.3.3.0/24, 4.0.0.0/24"
        comment: "Created by Ansible"
        color: "12"
    
    # BASIC FQDN NAT
    - name: EDIT FMGR_FIREWALL_FQDN
      fmgr_fwobj_vip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        name: "Basic FQDN Translation"
        mode: "set"
        adom: "ansible"
        type: "fqdn"
        mapped_addr: "google-play"
        comment: "Created by Ansible"
        color: "5"
    
    # DELETE AN ENTRY
    - name: DELETE FMGR_FIREWALL_VIP PNAT
      fmgr_fwobj_vip:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        name: "Basic PNAT Map Port 10443"
        mode: "delete"
        adom: "ansible"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

