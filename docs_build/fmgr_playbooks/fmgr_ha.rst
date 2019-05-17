=======
fmgr_ha
=======


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SET FORTIMANAGER HA NODE TO MASTER
      fmgr_ha:
        fmgr_ha_mode: "master"
        fmgr_ha_cluster_pw: "fortinet"
        fmgr_ha_cluster_id: "1"
    
    - name: SET FORTIMANAGER HA NODE TO SLAVE
      fmgr_ha:
        fmgr_ha_mode: "slave"
        fmgr_ha_cluster_pw: "fortinet"
        fmgr_ha_cluster_id: "1"
    
    - name: SET FORTIMANAGER HA NODE TO STANDALONE
      fmgr_ha:
        fmgr_ha_mode: "standalone"
    
    - name: ADD FORTIMANAGER HA PEER
      fmgr_ha:
        fmgr_ha_peer_ipv4: "192.168.1.254"
        fmgr_ha_peer_sn: "FMG-VM1234567890"
        fmgr_ha_peer_status: "enable"
    
    - name: CREATE CLUSTER ON MASTER
      fmgr_ha:
        fmgr_ha_mode: "master"
        fmgr_ha_cluster_pw: "fortinet"
        fmgr_ha_cluster_id: "1"
        fmgr_ha_hb_threshold: "10"
        fmgr_ha_hb_interval: "15"
        fmgr_ha_file_quota: "2048"



Playbook File Examples
----------------------


fmgr_ha_run_all.sh
++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_ha_run_all.sh -vvvv
    ansible-playbook fmgr_ha_standalone.yml -vvvv
    ansible-playbook fmgr_ha_enable_peer2.yml -vvvv
    ansible-playbook fmgr_ha_slave.yml -vvvv
    ansible-playbook fmgr_ha_enable_peer.yml -vvvv
    ansible-playbook fmgr_ha_enable_peer_slave.yml -vvvv
    ansible-playbook fmgr_ha_master.yml -vvvv
    ansible-playbook fmgr_ha_disable_peer2.yml -vvvv
    ansible-playbook fmgr_ha_disable_peer.yml -vvvv


fmgr_ha_standalone.yml
++++++++++++++++++++++

.. code-block:: yaml



    
    - name: SET FORTIMANAGER HA MODE TO STANDALONE
      hosts: FortiManager, FortiManagerSlave
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: SET FORTIMANAGER HA NODE TO STANDALONE
        fmgr_ha:
          fmgr_ha_mode: "standalone"

fmgr_ha_enable_peer2.yml
++++++++++++++++++++++++

.. code-block:: yaml



    - name: ADD FMG HA PEER
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: ENABLE FORTIMANAGER HA PEER
          fmgr_ha:
            fmgr_ha_peer_ipv4: "10.7.220.140"
            fmgr_ha_peer_sn: "FMG-VM0A17005535"
            fmgr_ha_peer_status: "enable"


fmgr_ha_slave.yml
+++++++++++++++++

.. code-block:: yaml



    - name: SET FORTIMANAGER HA MODE TO SLAVE
      hosts: FortiManagerSlave
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: SET FORTIMANAGER HA NODE TO SLAVE
          fmgr_ha:
            fmgr_ha_mode: "slave"
            fmgr_ha_cluster_pw: "fortinet"
            fmgr_ha_cluster_id: "2"

fmgr_ha_enable_peer.yml
+++++++++++++++++++++++

.. code-block:: yaml



    - name: ADD FMG HA PEER
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: ENABLE FORTIMANAGER HA PEER
          fmgr_ha:
            fmgr_ha_peer_ipv4: "10.7.220.36"
            fmgr_ha_peer_sn: "FMG-VMTM18001882"
            fmgr_ha_peer_status: "enable"


fmgr_ha_enable_peer_slave.yml
+++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: ADD FMG HA PEER
      hosts: FortiManagerSlave
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: ADD FORTIMANAGER HA PEER
          fmgr_ha:
            fmgr_ha_peer_ipv4: "10.7.220.35"
            fmgr_ha_peer_sn: "FMG-VMTM18001881"
            fmgr_ha_peer_status: "enable"
            fmgr_ha_mode: "slave"
            fmgr_ha_cluster_pw: "fortinet"
            fmgr_ha_cluster_id: "2"


fmgr_ha_master.yml
++++++++++++++++++

.. code-block:: yaml



    - name: SET FORTIMANAGER HA MODE TO MASTER
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: SET FORTIMANAGER HA NODE TO MASTER
          fmgr_ha:
            fmgr_ha_mode: "master"
            fmgr_ha_cluster_pw: "fortinet"
            fmgr_ha_cluster_id: "2"
            fmgr_ha_hb_threshold: "10"
            fmgr_ha_hb_interval: "15"
            fmgr_ha_file_quota: "2048"


fmgr_ha_disable_peer2.yml
+++++++++++++++++++++++++

.. code-block:: yaml



    - name: ADD FMG HA PEER
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISABLE FORTIMANAGER HA PEER
          fmgr_ha:
            fmgr_ha_peer_ipv4: "10.7.220.140"
            fmgr_ha_peer_sn: "FMG-VM0A17005535"
            fmgr_ha_peer_status: "disable"


fmgr_ha_disable_peer.yml
++++++++++++++++++++++++

.. code-block:: yaml



    - name: ADD FMG HA PEER
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DISABLE FORTIMANAGER HA PEER
          fmgr_ha:
            fmgr_ha_peer_ipv4: "10.7.220.36"
            fmgr_ha_peer_sn: "FMG-VMTM18001882"
            fmgr_ha_peer_status: "disable"




