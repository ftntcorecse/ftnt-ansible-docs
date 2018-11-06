==================
fmgr_fwobj_service
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: ADD A CUSTOM SERVICE FOR TCP/UDP/SCP
      fmgr_fwobj_service:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        name: "ansible_custom_service"
        object_type: "custom"
        custom_type: "tcp_udp_sctp"
        tcp_portrange: "443"
        udp_portrange: "51"
        sctp_portrange: "100"
    
    - name: ADD A CUSTOM SERVICE FOR TCP/UDP/SCP WITH SOURCE RANGES AND MULTIPLES
      fmgr_fwobj_service:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        name: "ansible_custom_serviceWithSource"
        object_type: "custom"
        custom_type: "tcp_udp_sctp"
        tcp_portrange: "443:2000-1000,80-82:10000-20000"
        udp_portrange: "51:100-200,162:200-400"
        sctp_portrange: "100:2000-2500"
    
    - name: ADD A CUSTOM SERVICE FOR ICMP
      fmgr_fwobj_service:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        name: "ansible_custom_icmp"
        object_type: "custom"
        custom_type: "icmp"
        icmp_type: "8"
        icmp_code: "3"
    
    - name: ADD A CUSTOM SERVICE FOR ICMP6
      fmgr_fwobj_service:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        name: "ansible_custom_icmp6"
        object_type: "custom"
        custom_type: "icmp6"
        icmp_type: "5"
        icmp_code: "1"
    
    - name: ADD A CUSTOM SERVICE FOR IP - GRE
      fmgr_fwobj_service:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        name: "ansible_custom_icmp6"
        object_type: "custom"
        custom_type: "ip"
        protocol_number: "47"
    
    - name: ADD A CUSTOM PROXY FOR ALL WITH SOURCE RANGES AND MULTIPLES
      fmgr_fwobj_service:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "ansible"
        name: "ansible_custom_proxy_all"
        object_type: "custom"
        custom_type: "all"
        explicit_proxy: "enable"
        tcp_portrange: "443:2000-1000,80-82:10000-20000"
        iprange: "www.ansible.com"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

