===============
fmgr_secprof_av
===============


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_av:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
          name: "Ansible_AV_Profile"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_av:
          host: "{{inventory_hostname}}"
          username: "{{ username }}"
          password: "{{ password }}"
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

%%PB_FILE_EXAMPLE_TOKEN%%

