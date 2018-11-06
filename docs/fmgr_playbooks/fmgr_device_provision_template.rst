==============================
fmgr_device_provision_template
==============================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SET SNMP SYSTEM INFO
      fmgr_device_provision_template:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "default"
        snmp_status: "enable"
        state: "present"
    
    - name: SET SNMP SYSTEM INFO ANSIBLE ADOM
      fmgr_device_provision_template:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "default"
        snmp_status: "enable"
        state: "present"
        adom: "ansible"
    
    - name: SET SNMP SYSTEM INFO different template (SNMPv2)
      fmgr_device_provision_template:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        snmp_status: "enable"
        state: "present"
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
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        snmp_status: "enable"
        state: "present"
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
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
        adom: "ansible"
        syslog_server: "10.7.220.59"
        syslog_port: "514"
        syslog_mode: "disable"
        syslog_status: "enable"
        syslog_filter: "information"
    
    - name: SET NTP TO FORTIGUARD
      fmgr_device_provision_template:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
        adom: "ansible"
        ntp_status: "enable"
        ntp_sync_interval: "60"
        type: "fortiguard"
    
    - name: SET NTP TO CUSTOM SERVER
      fmgr_device_provision_template:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
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
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
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
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
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
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
        adom: "ansible"
        dns_suffix: "ansible.local"
        dns_primary_ipv4: "8.8.8.8"
        dns_secondary_ipv4: "4.4.4.4"
    
    - name: SET PROVISIONING TEMPLATE DEVICE TARGETS IN FORTIMANAGER
      fmgr_device_provision_template:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        provisioning_template: "ansibleTest"
        state: "present"
        adom: "ansible"
        provision_targets: "FGT1, FGT2"
    
    - name: DELETE ENTIRE PROVISIONING TEMPLATE
      fmgr_device_provision_template:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        delete_provisioning_template: "ansibleTest"
        state: "absent"
        adom: "ansible"
    



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

