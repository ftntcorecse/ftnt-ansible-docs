==================
fmgr_device_config
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CHANGE HOSTNAME
      fmgr_device_config:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        device_hostname: "ChangedbyAnsible"
        device_unique_name: "FGT1"
    
    - name: EDIT INTERFACE INFORMATION
      fmgr_device_config:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_unique_name: "FGT2"
        interface: "port3"
        interface_ip: "10.1.1.1/24"
        interface_allow_access: "ping, telnet, https"
    
    - name: INSTALL CONFIG
      fmgr_device_config:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_unique_name: "FGT1"
        install_config: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

