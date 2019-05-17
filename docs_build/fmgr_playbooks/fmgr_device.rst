===========
fmgr_device
===========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: DISCOVER AND ADD DEVICE FGT1
      fmgr_device:
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.201"
        device_unique_name: "FGT1"
        device_serial: "FGVM000000117994"
        mode: "add"
        blind_add: "enable"
    
    - name: DISCOVER AND ADD DEVICE FGT2
      fmgr_device:
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.202"
        device_unique_name: "FGT2"
        device_serial: "FGVM000000117992"
        mode: "delete"



Playbook File Examples
----------------------


fmgr_devices_ansibleAdom.yml
++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            #hard coded fortimanager example host and login -- see "fmg_group_add.yml for ansible host file version"
            #HARD CODED LOGIN FOR FORTIMANAGER SEE "fmg_group_add.yml" example for anisble host version
            #ADOM TO ADD THE DEVICE TO
            adom: "ansible"
            #DEVICE LOGIN
            device_username: "admin"
            device_password: "fortinet"
            #DEVICE IP ADDRESS
            device_ip: "10.7.220.151"
            #FRIENDLY NAME FOR DEVICE IN FORTIMANAGER
            device_unique_name: "FGT1"
        - name: DISCOVER AND ADD DEVICE FGT2
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.152"
            device_unique_name: "FGT2"
        - name: DISCOVER AND ADD DEVICE FGT3
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.153"
            device_unique_name: "FGT3"


fmgr_device_run_all.sh
++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_devices_ansibleAdom.yml -vvvv
    ansible-playbook fmgr_devices_plugin_edition_add.yml -vvvv
    ansible-playbook fmgr_devices_ansibleAdom_all.yml -vvvv
    ansible-playbook fmgr_devices_delete_ansibleAdom.yml -vvvv
    ansible-playbook fmgr_devices_plugin_edition_del.yml -vvvv
    ansible-playbook fmgr_devices.yml -vvvv
    ansible-playbook fmgr_devices_ipv6_add.yml -vvvv
    ansible-playbook fmgr_devices_ansibleAdom2.yml -vvvv


fmgr_devices_plugin_edition_add.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES via PLUGIN
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.151"
            device_unique_name: "FGT1"
            mode: "add"
          ignore_errors: yes
          ignore_unreachable: yes
    
        - name: DISCOVER AND ADD DEVICE FGT2
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.152"
            device_unique_name: "FGT2"
            #blind_add: "enable"
          ignore_errors: yes
          ignore_unreachable: yes
    
        - name: DISCOVER AND ADD DEVICE FGT3
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.153"
            device_unique_name: "FGT3"
          ignore_errors: yes
          ignore_unreachable: yes


fmgr_devices_ansibleAdom_all.yml
++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT4
          fmgr_device:
            adom: "ansible"
            #DEVICE LOGIN
            device_username: "admin"
            device_password: "fortinet"
            #DEVICE IP ADDRESS
            device_ip: "10.7.220.164"
            #FRIENDLY NAME FOR DEVICE IN FORTIMANAGER
            device_unique_name: "FGT4"
        - name: DISCOVER AND ADD DEVICE FGT5
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.165"
            device_unique_name: "FGT5"
        - name: DISCOVER AND ADD DEVICE FGT6
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.166"
            device_unique_name: "FGT6"
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            adom: "ansible"
            #DEVICE LOGIN
            device_username: "admin"
            device_password: "fortinet"
            #DEVICE IP ADDRESS
            device_ip: "10.7.220.151"
            #FRIENDLY NAME FOR DEVICE IN FORTIMANAGER
            device_unique_name: "FGT1"
        - name: DISCOVER AND ADD DEVICE FGT2
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.152"
            device_unique_name: "FGT2"
        - name: DISCOVER AND ADD DEVICE FGT3
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.153"
            device_unique_name: "FGT3"

fmgr_devices_delete_ansibleAdom.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            #hard coded fortimanager example host and login -- see "fmg_group_add.yml for ansible host file version"
            #HARD CODED LOGIN FOR FORTIMANAGER SEE "fmg_group_add.yml" example for anisble host version
            #ADOM TO ADD THE DEVICE TO
            adom: "ansible"
            #DEVICE LOGIN
            device_username: "admin"
            device_password: "fortinet"
            #DEVICE IP ADDRESS
            device_ip: "10.7.220.151"
            #FRIENDLY NAME FOR DEVICE IN FORTIMANAGER
            device_unique_name: "FGT1"
            #SERIAL NUMBER OF DEVICE
            state: "absent"
        - name: DISCOVER AND ADD DEVICE FGT2
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.152"
            device_unique_name: "FGT2"
            state: "absent"
        - name: DISCOVER AND ADD DEVICE FGT3
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.153"
            device_unique_name: "FGT3"
            state: "absent"


fmgr_devices_plugin_edition_del.yml
+++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES via PLUGIN
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.151"
            device_unique_name: "FGT1"
            mode: "delete"
    #      ignore_errors: yes
    
        - name: DISCOVER AND ADD DEVICE FGT2
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.152"
            device_unique_name: "FGT2"
            mode: "delete"
    #      ignore_errors: yes
    
        - name: DISCOVER AND ADD DEVICE FGT3
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.153"
            device_unique_name: "FGT3"
            mode: "delete"
    #      ignore_errors: yes


fmgr_devices.yml
++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            adom: "root"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.10.24.201"
            device_unique_name: "FGT1"
            device_serial: "FGVM000000117994"
        - name: DISCOVER AND ADD DEVICE FGT2
          fmgr_device:
            adom: "root"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.10.24.202"
            device_unique_name: "FGT2"
            device_serial: "FGVM000000117992"


fmgr_devices_ipv6_add.yml
+++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1 IPv6
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "fdc3:7fb3:8b9f:468b::2001"
            device_unique_name: "FGT1"


fmgr_devices_ansibleAdom2.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT4
          fmgr_device:
            #hard coded fortimanager example host and login -- see "fmg_group_add.yml for ansible host file version"
            #HARD CODED LOGIN FOR FORTIMANAGER SEE "fmg_group_add.yml" example for anisble host version
            #ADOM TO ADD THE DEVICE TO
            adom: "ansible"
            #DEVICE LOGIN
            device_username: "admin"
            device_password: "fortinet"
            #DEVICE IP ADDRESS
            device_ip: "10.7.220.164"
            #FRIENDLY NAME FOR DEVICE IN FORTIMANAGER
            device_unique_name: "FGT4"
        - name: DISCOVER AND ADD DEVICE FGT5
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.165"
            device_unique_name: "FGT5"
        - name: DISCOVER AND ADD DEVICE FGT6
          fmgr_device:
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.166"
            device_unique_name: "FGT6"


fmgr_devices_pyfmg.yml
++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
        - name: DISCOVER AND ADD DEVICE FGT1
          fmgr_device:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            adom: "ansible"
            device_username: "admin"
            device_password: "fortinet"
            device_ip: "10.7.220.151"
            device_unique_name: "FGT1"
    #    - name: DISCOVER AND ADD DEVICE FGT2
    #      fmgr_device:
    #        host: "{{ inventory_hostname }}"
    #        username: "{{ username }}"
    #        password: "{{ password }}"
    #        adom: "ansible"
    #        device_username: "admin"
    #        device_password: "fortinet"
    #        device_ip: "10.7.220.152"
    #        device_unique_name: "FGT2"
    #    - name: DISCOVER AND ADD DEVICE FGT3
    #      fmgr_device:
    #        host: "{{ inventory_hostname }}"
    #        username: "{{ username }}"
    #        password: "{{ password }}"
    #        adom: "ansible"
    #        device_username: "admin"
    #        device_password: "fortinet"
    #        device_ip: "10.7.220.153"
    #        device_unique_name: "FGT3"




