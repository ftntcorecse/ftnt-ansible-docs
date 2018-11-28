==========
faz_device
==========


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

%%PB_FILE_EXAMPLE_TOKEN%%

