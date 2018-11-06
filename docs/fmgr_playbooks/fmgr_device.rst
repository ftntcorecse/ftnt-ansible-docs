===========
fmgr_device
===========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: DISCOVER AND ADD DEVICE FGT1
      fmgr_device:
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
    
    - name: DISCOVER AND ADD DEVICE FGT2
      fmgr_device:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.202"
        device_unique_name: "FGT2"
        device_serial: "FGVM000000117992"
        state: "absent"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

