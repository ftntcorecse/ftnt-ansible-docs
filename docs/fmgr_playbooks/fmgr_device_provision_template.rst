==============================
fmgr_device_provision_template
==============================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SET SNMP SYSTEM INFO
      fmgr_device_provision_template:
        provisioning_template: "default"
        snmp_status: "enable"
        mode: "set"
    
    - name: SET SNMP SYSTEM INFO ANSIBLE ADOM
      fmgr_device_provision_template:
        provisioning_template: "default"
        snmp_status: "enable"
        mode: "set"
        adom: "ansible"
    
    - name: SET SNMP SYSTEM INFO different template (SNMPv2)
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        snmp_status: "enable"
        mode: "set"
        adom: "ansible"
        snmp_v2c_query_port: "162"
        snmp_v2c_trap_port: "161"
        snmp_v2c_status: "enable"
        snmp_v2c_trap_status: "enable"
        snmp_v2c_query_status: "enable"
        snmp_v2c_name: "ansibleV2c"
        snmp_v2c_id: "1"
        snmp_v2c_trap_src_ipv4: "10.7.220.41"
        snmp_v2c_trap_hosts_ipv4: "10.7.220.59 255.255.255.255, 10.7.220.60 255.255.255.255"
        snmp_v2c_query_hosts_ipv4: "10.7.220.59 255.255.255.255, 10.7.220.0 255.255.255.0"
    
    - name: SET SNMP SYSTEM INFO different template (SNMPv3)
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        snmp_status: "enable"
        mode: "set"
        adom: "ansible"
        snmpv3_auth_proto: "sha"
        snmpv3_auth_pwd: "fortinet"
        snmpv3_name: "ansibleSNMPv3"
        snmpv3_notify_hosts: "10.7.220.59,10.7.220.60"
        snmpv3_priv_proto: "aes256"
        snmpv3_priv_pwd: "fortinet"
        snmpv3_queries: "enable"
        snmpv3_query_port: "161"
        snmpv3_security_level: "auth_priv"
        snmpv3_source_ip: "0.0.0.0"
        snmpv3_status: "enable"
        snmpv3_trap_rport: "162"
        snmpv3_trap_status: "enable"
    
    - name: SET SYSLOG INFO
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        syslog_server: "10.7.220.59"
        syslog_port: "514"
        syslog_mode: "disable"
        syslog_status: "enable"
        syslog_filter: "information"
    
    - name: SET NTP TO FORTIGUARD
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        ntp_status: "enable"
        ntp_sync_interval: "60"
        type: "fortiguard"
    
    - name: SET NTP TO CUSTOM SERVER
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        ntp_status: "enable"
        ntp_sync_interval: "60"
        ntp_type: "custom"
        ntp_server: "10.7.220.32,10.7.220.1"
        ntp_auth: "enable"
        ntp_auth_pwd: "fortinet"
        ntp_v3: "disable"
    
    - name: SET ADMIN GLOBAL SETTINGS
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        admin_https_redirect: "enable"
        admin_https_port: "4433"
        admin_http_port: "8080"
        admin_timeout: "30"
        admin_language: "english"
        admin_switch_controller: "enable"
        admin_gui_theme: "blue"
        admin_enable_fortiguard: "direct"
        admin_fortiguard_target: "10.7.220.128"
        admin_fortianalyzer_target: "10.7.220.61"
    
    - name: SET CUSTOM SMTP SERVER
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        smtp_username: "ansible"
        smtp_password: "fortinet"
        smtp_port: "25"
        smtp_replyto: "ansible@do-not-reply.com"
        smtp_conn_sec: "starttls"
        smtp_server: "10.7.220.32"
        smtp_source_ipv4: "0.0.0.0"
        smtp_validate_cert: "disable"
    
    - name: SET DNS SERVERS
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        dns_suffix: "ansible.local"
        dns_primary_ipv4: "8.8.8.8"
        dns_secondary_ipv4: "4.4.4.4"
    
    - name: SET PROVISIONING TEMPLATE DEVICE TARGETS IN FORTIMANAGER
      fmgr_device_provision_template:
        provisioning_template: "ansibleTest"
        mode: "set"
        adom: "ansible"
        provision_targets: "FGT1, FGT2"
    
    - name: DELETE ENTIRE PROVISIONING TEMPLATE
      fmgr_device_provision_template:
        delete_provisioning_template: "ansibleTest"
        mode: "delete"
        adom: "ansible"
    



Playbook File Examples
----------------------


fmgr_device_provision_template_remove_scope.yml
+++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DELETE DEVICE PROVISION TEMPLATES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: SET PROVISIONING TEMPLATE DEVICE TARGETS IN FORTIMANAGER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            provision_targets: "FGT1,FGT2"

fmgr_device_proftemplate_faz_assign.yml
+++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: CREATE DEVICE PROVISION TEMPLATES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    #    - name: SET ADMIN GLOBAL SETTINGS
    #      fmgr_device_provision_template:
    #        provisioning_template: "testTemplate"
    #        mode: "set"
    #        adom: "ansible"
    #        admin_https_redirect: "enable"
    #        admin_timeout: "60"
    #        admin_gui_theme: "blue"
    #        admin_fortianalyzer_target: "10.7.220.38"
    #
    #    - name: SET PROVISIONING TEMPLATE DEVICE TARGETS IN FORTIMANAGER
    #      fmgr_device_provision_template:
    #        provisioning_template: "testTemplate"
    #        mode: "set"
    #        adom: "ansible"
    #        provision_targets: "seattle-fgt-cluster"
    
    
        - name: INSTALL CONFIG
          fmgr_device_config:
            adom: "ansible"
            device_unique_name: "seattle-fgt-cluster"
            install_config: "enable"
    
    
    
    


fmgr_device_provision_template_delete.yml
+++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: CREATE DEVICE PROVISION TEMPLATES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DELETE ENTIRE PROVISIONING TEMPLATE
          fmgr_device_provision_template:
            delete_provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"

fmgr_device_provision_template.yml
++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: CREATE DEVICE PROVISION TEMPLATES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: SET SNMP SYSTEM INFO ANSIBLE ADOM
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "set"
            adom: "ansible"
    
        - name: SET SYSLOG INFO
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            syslog_server: "10.7.220.59"
            syslog_port: "514"
            syslog_mode: "udp"
            syslog_status: "enable"
            syslog_filter: "critical"
            syslog_facility: "kernel"
    
        - name: SET SNMP SYSTEM INFO different template
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "set"
            adom: "ansible"
            snmp_v2c_query_port: "162"
            snmp_v2c_trap_port: "161"
            snmp_v2c_status: "enable"
            snmp_v2c_trap_status: "enable"
            snmp_v2c_query_status: "enable"
            snmp_v2c_name: "ansibleV2c"
            snmp_v2c_id: "1"
            snmp_v2c_trap_src_ipv4: "10.7.220.41"
            snmp_v2c_trap_hosts_ipv4: "10.7.220.59 255.255.255.255, 10.7.220.60 255.255.255.255"
            snmp_v2c_query_hosts_ipv4: "10.7.220.59 255.255.255.255, 10.7.220.0 255.255.255.0"
    
    
        - name: SET SNMP SYSTEM INFO different template (SNMPv3)
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "set"
            adom: "ansible"
            snmpv3_auth_proto: "sha"
            snmpv3_auth_pwd: "fortinet"
            snmpv3_name: "ansibleSNMPv3"
            snmpv3_notify_hosts: "10.7.220.59,10.7.220.60"
            snmpv3_priv_proto: "aes256"
            snmpv3_priv_pwd: "fortinet"
            snmpv3_queries: "enable"
            snmpv3_query_port: "161"
            snmpv3_security_level: "auth-priv"
            snmpv3_source_ip: "0.0.0.0"
            snmpv3_status: "enable"
            snmpv3_trap_rport: "162"
            snmpv3_trap_status: "enable"
    
        - name: SET NTP TO FORTIGUARD
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            ntp_status: "enable"
            ntp_sync_interval: "60"
            ntp_type: "fortiguard"
    
        - name: SET NTP TO CUSTOM SERVER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            ntp_status: "enable"
            ntp_sync_interval: "60"
            ntp_type: "custom"
            ntp_server: "10.7.220.32,10.7.220.1"
            ntp_auth: "enable"
            ntp_auth_pwd: "fortinet"
    
        - name: SET ADMIN GLOBAL SETTINGS
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            admin_https_redirect: "enable"
            admin_https_port: "4433"
            admin_http_port: "8080"
            admin_timeout: "60"
            admin_language: "english"
            admin_switch_controller: "enable"
            admin_gui_theme: "blue"
            admin_enable_fortiguard: "this-fmg"
            #admin_fortiguard_target: "10.7.220.128"
            admin_fortianalyzer_target: "10.7.220.38"
    
        - name: SET CUSTOM SMTP SERVER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            smtp_username: "ansible"
            smtp_password: "{{ password }}"
            smtp_port: "25"
            smtp_replyto: "ansible@do-not-reply.com"
            smtp_conn_sec: "starttls"
            smtp_server: "10.7.220.32"
            smtp_source_ipv4: "0.0.0.0"
            smtp_validate_cert: "disable"
    
        - name: SET DNS SERVERS
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            dns_suffix: "ansible.local"
            dns_primary_ipv4: "8.8.8.8"
            dns_secondary_ipv4: "4.4.4.4"
    
        - name: SET PROVISIONING TEMPLATE DEVICE TARGETS IN FORTIMANAGER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "set"
            adom: "ansible"
            provision_targets: "FGT1,FGT2"


fmgr_device_provision_template_run_all.sh
+++++++++++++++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_device_provision_template_remove_scope.yml -vvvv
    ansible-playbook fmgr_device_proftemplate_faz_assign.yml -vvvv
    ansible-playbook fmgr_device_provision_template_delete.yml -vvvv
    ansible-playbook fmgr_device_provision_template.yml -vvvv
    ansible-playbook fmgr_device_provision_template_run_all.sh -vvvv
    ansible-playbook fmgr_device_provision_template_absent.yml -vvvv


fmgr_device_provision_template_absent.yml
+++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DELETE DEVICE PROVISION TEMPLATES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: DELETE SNMP SYSTEM INFO
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "delete"
            adom: "ansible"
    
        - name: DELETE SNMP SYSTEM INFO ANSIBLE ADOM
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "delete"
            adom: "ansible"
    
        - name: DELETE SYSLOG INFO
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            syslog_server: "10.7.220.59"
            syslog_port: "514"
            syslog_mode: "udp"
            syslog_status: "enable"
            syslog_filter: "critical"
    
        - name: DELETE SNMP SYSTEM INFO different template
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "delete"
            adom: "ansible"
            snmp_v2c_query_port: "162"
            snmp_v2c_trap_port: "161"
            snmp_v2c_status: "enable"
            snmp_v2c_trap_status: "enable"
            snmp_v2c_query_status: "enable"
            snmp_v2c_name: "ansibleV2c"
            snmp_v2c_id: "1"
            snmp_v2c_trap_src_ipv4: "10.7.220.41"
            snmp_v2c_trap_hosts_ipv4: "10.7.220.59 255.255.255.255, 10.7.220.60 255.255.255.255"
            snmp_v2c_query_hosts_ipv4: "10.7.220.59 255.255.255.255, 10.7.220.0 255.255.255.0"
    
        - name: DELETE SNMP SYSTEM INFO different template (SNMPv3)
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            snmp_status: "enable"
            mode: "delete"
            adom: "ansible"
            snmpv3_auth_proto: "sha"
            snmpv3_auth_pwd: "fortinet"
            snmpv3_name: "ansibleSNMPv3"
            snmpv3_notify_hosts: "10.7.220.59,10.7.220.60"
            snmpv3_priv_proto: "aes256"
            snmpv3_priv_pwd: "fortinet"
            snmpv3_queries: "enable"
            snmpv3_query_port: "161"
            snmpv3_security_level: "auth-priv"
            snmpv3_source_ip: "0.0.0.0"
            snmpv3_status: "enable"
            snmpv3_trap_rport: "162"
            snmpv3_trap_status: "enable"
    
        - name: DELETE NTP TO FORTIGUARD
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            ntp_status: "enable"
            ntp_sync_interval: "60"
            ntp_type: "fortiguard"
    
        - name: DELETE NTP TO CUSTOM SERVER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            ntp_status: "enable"
            ntp_sync_interval: "60"
            ntp_type: "custom"
            ntp_server: "10.7.220.32,10.7.220.1"
            ntp_auth: "enable"
            ntp_auth_pwd: "fortinet"
            ntp_v3: "disable"
    
        - name: DELETE ADMIN GLOBAL DELETETINGS
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            admin_https_redirect: "enable"
            admin_https_port: "4433"
            admin_http_port: "8080"
            admin_timeout: "30"
            admin_language: "english"
            admin_switch_controller: "enable"
            admin_gui_theme: "blue"
            admin_enable_fortiguard: "none"
            admin_fortianalyzer_target: "10.7.220.65"
    
        - name: DELETE CUSTOM SMTP SERVER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            smtp_username: "ansible"
            smtp_password: "{{ password }}"
            smtp_port: "25"
            smtp_replyto: "ansible@do-not-reply.com"
            smtp_conn_sec: "starttls"
            smtp_server: "10.7.220.32"
            smtp_source_ipv4: "0.0.0.0"
            smtp_validate_cert: "disable"
    
        - name: SET DNS SERVERS
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            dns_suffix: "ansible.local"
            dns_primary_ipv4: "8.8.8.8"
            dns_secondary_ipv4: "4.4.4.4"
    
        - name: SET PROVISIONING TEMPLATE DEVICE TARGETS IN FORTIMANAGER
          fmgr_device_provision_template:
            provisioning_template: "ansibleTest"
            mode: "delete"
            adom: "ansible"
            provision_targets: "FGT1,FGT2"



