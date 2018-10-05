==========
faz_device
==========

Not Parsed


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: DISCOVER AND ADD DEVICE A PHYSICAL FORTIGATE
      faz_device:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.201"
        device_unique_name: "FGT1"
        device_serial: "FGVM000000117994"
        state: "present"
        mgmt_mode: "faz"
        os_type: "fos"
        os_ver: "5.0"
        minor_rev: 6
        
    
    - name: DISCOVER AND ADD DEVICE A VIRTUAL FORTIGATE
      faz_device:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.202"
        device_unique_name: "FGT2"
        mgmt_mode: "faz"
        os_type: "fos"
        os_ver: "5.0"
        minor_rev: 6
        state: "present"
        platform_str: "FortiGate-VM64"



Playbook File Examples
----------------------


faz_device_add.yml
++++++++++++++++++

.. code-block:: yaml


    - name: "ADD FAZ DEVICE"
      connection: local
      gather_facts: false
      hosts: FortiAnalyzer
    
      tasks:
        - name: DISCOVER AND ADD DEVICE A VIRTUAL FORTIGATE
          faz_device:
            host: "{{inventory_hostname}}"
            username: "{{ username }}"
            password: "{{ password }}"
            adom: "root"
            device_ip: "10.7.220.151"
            device_password: "fortinet"
            device_unique_name: "FGT01"
            device_username: "ansible"
            mgmt_mode: "faz"
            os_minor_vers: 6
            os_type: "fos"
            os_ver: "5.0"
            platform_str: "FortiGate-VM64"
            state: "present"
            device_serial: "FGVM010000122995"
    


faz_device_del.yml
++++++++++++++++++

.. code-block:: yaml


    - name: "DELETE FAZ DEVICE"
      connection: local
      gather_facts: false
      hosts: FortiAnalyzer
    
      tasks:
        - name: DELETE VIRTUAL FORTIGATE
          faz_device:
            host: "{{inventory_hostname}}"
            username: "{{ username }}"
            password: "{{ password }}"
            adom: "root"
            device_unique_name: "FGT01"
            state: "absent"

faz_device_promote_unreg.yml
++++++++++++++++++++++++++++

.. code-block:: yaml


    - name: "ADD FAZ DEVICE"
      connection: local
      gather_facts: false
      hosts: FortiAnalyzer
    
      tasks:
    #    - name: PROMOTE CLUSTER 1 IN FAZ
    #      faz_device:
    #        host: "{{inventory_hostname}}"
    #        username: "{{ username }}"
    #        password: "{{ password }}"
    #        adom: "root"
    #        device_password: "fortinet"
    #        device_unique_name: "seattle-fgt-cluster"
    #        device_username: "ansible"
    #        mgmt_mode: "faz"
    #        state: "present"
    #        device_action: "promote_unreg"
    
    
        - name: PROMOTE CLUSTER 2 IN FAZ
          faz_device:
            host: "{{inventory_hostname}}"
            username: "{{ username }}"
            password: "{{ password }}"
            adom: "root"
            device_password: "fortinet"
            device_unique_name: "nyc-fgt-cluster"
            device_username: "ansible"
            mgmt_mode: "faz"
            state: "present"
            device_action: "promote_unreg"




