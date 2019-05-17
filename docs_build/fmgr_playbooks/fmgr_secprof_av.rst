===============
fmgr_secprof_av
===============


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_av:
          name: "Ansible_AV_Profile"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_av:
          name: "Ansible_AV_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          inspection_mode: "proxy"
          ftgd_analytics: "everything"
          av_block_log: "enable"
          av_virus_log: "enable"
          scan_mode: "full"
          mobile_malware_db: "enable"
          ftp_archive_block: "encrypted"
          ftp_outbreak_prevention: "files"
          ftp_archive_log: "timeout"
          ftp_emulator: "disable"
          ftp_options: "scan"



Playbook File Examples
----------------------


fmgr_secprof_av_run_all.sh
++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_secprof_av_add.yml -vvvv
    ansible-playbook fmgr_secprof_av_del.yml -vvvv
    ansible-playbook av.yml -vvvv


fmgr_secprof_av_add.yml
+++++++++++++++++++++++

.. code-block:: yaml



    - name: SET FORTIMANAGER HA MODE TO SLAVE
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: CREATE Profile
          fmgr_secprof_av:
            name: "Ansible_AV_Profile"
            comment: "Created by Ansible Module TEST"
            mode: "set"
            inspection_mode: "proxy"
            ftgd_analytics: "everything"
            av_block_log: "enable"
            av_virus_log: "enable"
            scan_mode: "full"
            mobile_malware_db: "enable"
            ftp_archive_block: "encrypted"
            ftp_outbreak_prevention: "files"
            ftp_archive_log: "timeout"
            ftp_emulator: "disable"
            ftp_options: "scan"
            adom: "ansible"

fmgr_secprof_av_del.yml
+++++++++++++++++++++++

.. code-block:: yaml



    - name: SET FORTIMANAGER HA MODE TO SLAVE
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DELETE Profile
          fmgr_secprof_av:
            name: "Ansible_AV_Profile"
            mode: "delete"

av.yml
++++++

.. code-block:: yaml



    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE Profile
        fmgr_secprof_av:
          name: "Ansible_AV_Profile"
          mode: "delete"
          adom: "ansible"
    
    
      - name: CREATE Profile
        fmgr_secprof_av:
          name: "Ansible_AV_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          adom: "ansible"
          inspection_mode: "proxy"
          ftgd_analytics: "everything"
          av_block_log: "enable"
          av_virus_log: "enable"
          scan_mode: "full"
          mobile_malware_db: "enable"
          ftp_archive_block: "encrypted"
          ftp_outbreak_prevention: "files"
          ftp_archive_log: "timeout"
          ftp_emulator: "disable"
          ftp_options: "scan"



