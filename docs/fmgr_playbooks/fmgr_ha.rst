=======
fmgr_ha
=======


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SET FORTIMANAGER HA NODE TO MASTER
      fmgr_ha:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        fmgr_ha_mode: "master"
    
    - name: SET FORTIMANAGER HA NODE TO SLAVE
      fmgr_ha:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        fmgr_ha_mode: "slave"
    
    - name: SET FORTIMANAGER HA NODE TO STANDALONE
      fmgr_ha:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        fmgr_ha_mode: "standalone"
    
    - name: ADD FORTIMANAGER HA PEER
      fmgr_ha:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        fmgr_ha_peer_ipv4: "10.7.220.36"
        fmgr_ha_peer_sn: "FMG-VM0A17002010"
        fmgr_ha_peer_status: "enable"
    
    - name: CREATE CLUSTER ON MASTER
      fmgr_ha:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        fmgr_ha_mode: "master"
        fmgr_ha_cluster_pw: "fortinet"
        fmgr_ha_cluster_id: "1"
        fmgr_ha_hb_threshold: "10"
        fmgr_ha_hb_interval: "15"
        fmgr_ha_file_quota: "2048"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

