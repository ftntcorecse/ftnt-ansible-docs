==================
fmgr_fwobj_service
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: ADD A CUSTOM SERVICE FOR TCP/UDP/SCP
      fmgr_fwobj_service:
        adom: "ansible"
        name: "ansible_custom_service"
        object_type: "custom"
        custom_type: "tcp_udp_sctp"
        tcp_portrange: "443"
        udp_portrange: "51"
        sctp_portrange: "100"
    
    - name: ADD A CUSTOM SERVICE FOR TCP/UDP/SCP WITH SOURCE RANGES AND MULTIPLES
      fmgr_fwobj_service:
        adom: "ansible"
        name: "ansible_custom_serviceWithSource"
        object_type: "custom"
        custom_type: "tcp_udp_sctp"
        tcp_portrange: "443:2000-1000,80-82:10000-20000"
        udp_portrange: "51:100-200,162:200-400"
        sctp_portrange: "100:2000-2500"
    
    - name: ADD A CUSTOM SERVICE FOR ICMP
      fmgr_fwobj_service:
        adom: "ansible"
        name: "ansible_custom_icmp"
        object_type: "custom"
        custom_type: "icmp"
        icmp_type: "8"
        icmp_code: "3"
    
    - name: ADD A CUSTOM SERVICE FOR ICMP6
      fmgr_fwobj_service:
        adom: "ansible"
        name: "ansible_custom_icmp6"
        object_type: "custom"
        custom_type: "icmp6"
        icmp_type: "5"
        icmp_code: "1"
    
    - name: ADD A CUSTOM SERVICE FOR IP - GRE
      fmgr_fwobj_service:
        adom: "ansible"
        name: "ansible_custom_icmp6"
        object_type: "custom"
        custom_type: "ip"
        protocol_number: "47"
    
    - name: ADD A CUSTOM PROXY FOR ALL WITH SOURCE RANGES AND MULTIPLES
      fmgr_fwobj_service:
        adom: "ansible"
        name: "ansible_custom_proxy_all"
        object_type: "custom"
        custom_type: "all"
        explicit_proxy: "enable"
        tcp_portrange: "443:2000-1000,80-82:10000-20000"
        iprange: "www.ansible.com"



Playbook File Examples
----------------------


fmgr_fwobj_service_run_all.sh
+++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_fwobj_service_delete_group.yml -vvvv
    ansible-playbook fmgr_fwobj_service_add_group.yml -vvvv
    ansible-playbook fmgr_fwobj_service_delete_custom.yml -vvvv
    ansible-playbook fmgr_fwobj_service_delete_category.yml -vvvv
    ansible-playbook fmgr_fwobj_service_add_custom.yml -vvvv
    ansible-playbook fmgr_fwobj_service_add_category.yml -vvvv


fmgr_fwobj_service_delete_group.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG CUSTOM SERVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD A CUSTOM SERVICE GROUP
        fmgr_fwobj_service:
          adom: "ansible"
          object_type: "group"
          group_name: "ansibleTestGroup"
          mode: "delete"

fmgr_fwobj_service_add_group.yml
++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG CUSTOM SERVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD A CUSTOM SERVICE GROUP
        fmgr_fwobj_service:
          adom: "ansible"
          object_type: "group"
          comment: "created by ansible"
          group_name: "ansibleTestGroup"
          group_member: "ansible_custom_ip, ansible_custom_icmp, ansible_custom_service"
          color: "10"

fmgr_fwobj_service_delete_custom.yml
++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG CUSTOM SERVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: REMOVE A CUSTOM SERVICE FOR TCP/UDP/SCP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_service"
          object_type: "custom"
          mode: "delete"
    
      - name: REMOVE A CUSTOM SERVICE FOR TCP/UDP/SCP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_icmp"
          object_type: "custom"
          mode: "delete"
    
      - name: REMOVE A CUSTOM SERVICE FOR TCP/UDP/SCP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_icmp6"
          object_type: "custom"
          mode: "delete"
    
      - name: REMOVE A CUSTOM SERVICE FOR TCP/UDP/SCP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_ip"
          object_type: "custom"
          mode: "delete"
    
      - name: REMOVE A CUSTOM SERVICE FOR TCP/UDP/SCP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_serviceWithSource"
          object_type: "custom"
          mode: "delete"
    
      - name: REMOVE A CUSTOM PROXY ALL
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_proxy_all"
          object_type: "custom"
          mode: "delete"
    


fmgr_fwobj_service_delete_category.yml
++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG CUSTOM SERVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE A CUSTOM SERVICE CATEGORY
        fmgr_fwobj_service:
          adom: "ansible"
          object_type: "category"
          category: "ansibleCategory5"
          mode: "delete"
    
      - name: DELETE A CUSTOM SERVICE CATEGORY 2
        fmgr_fwobj_service:
          adom: "ansible"
          object_type: "category"
          category: "ansibleCategory2"
          mode: "delete"
    
      - name: DELETE A CUSTOM SERVICE CATEGORY 3
        fmgr_fwobj_service:
          adom: "ansible"
          object_type: "category"
          category: "ansibleCategory"
          mode: "delete"

fmgr_fwobj_service_add_custom.yml
+++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG CUSTOM SERVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD A CUSTOM SERVICE FOR TCP/UDP/SCP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_service"
          object_type: "custom"
          custom_type: "tcp_udp_sctp"
          tcp_portrange: "443"
          udp_portrange: "51"
          sctp_portrange: "100"
          category: "ansibleCategoryTest"
    
      - name: ADD A CUSTOM SERVICE FOR TCP/UDP/SCP WITH SOURCE RANGES AND MULTIPLES
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_serviceWithSource"
          object_type: "custom"
          custom_type: "tcp_udp_sctp"
          tcp_portrange: "443:1000-2000,80-82:10000-20000"
          udp_portrange: "51:100-200,162:200-400"
          sctp_portrange: "100:2000-2500"
    
      - name: ADD A CUSTOM SERVICE FOR ICMP
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_icmp"
          object_type: "custom"
          custom_type: "icmp"
          icmp_type: "8"
          icmp_code: "3"
    
      - name: ADD A CUSTOM SERVICE FOR ICMP6
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_icmp6"
          object_type: "custom"
          custom_type: "icmp6"
          icmp_type: "5"
          icmp_code: "1"
    
      - name: ADD A CUSTOM SERVICE FOR IP - GRE
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_ip"
          object_type: "custom"
          custom_type: "ip"
          protocol_number: "12"
    
      - name: ADD A CUSTOM PROXY FOR ALL WITH SOURCE RANGES AND MULTIPLES
        fmgr_fwobj_service:
          adom: "ansible"
          name: "ansible_custom_proxy_all"
          object_type: "custom"
          custom_type: "all"
          explicit_proxy: "enable"
          tcp_portrange: "443:1000-2000,80-82:10000-20000"
          iprange: "www.ansible.com"

fmgr_fwobj_service_add_category.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG CUSTOM SERVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: ADD A CUSTOM SERVICE CATEGORY
        fmgr_fwobj_service:
          adom: "ansible"
          object_type: "category"
          comment: "created by ansible"
          category: "ansibleCategory5"
          mode: "set"



