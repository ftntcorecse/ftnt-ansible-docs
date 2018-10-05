===============
fmgr_ips_sensor
===============

Not Parsed


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: EDIT FMGR_IPS_SENSOR
      fmgr_ips_sensor:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        mode:
        adom:
        replacemsg_group:
        name:
        extended_log:
        comment:
        block_malicious_url:
        entries_action:
        entries_application:
        entries_location:
        entries_log:
        entries_log_attack_context:
        entries_log_packet:
        entries_os:
        entries_protocol:
        entries_quarantine:
        entries_quarantine_expiry:
        entries_quarantine_log:
        entries_rate_count:
        entries_rate_duration:
        entries_rate_mode:
        entries_rate_track:
        entries_rule:
        entries_severity:
        entries_status:
        entries_exempt_ip_dst_ip:
        entries_exempt_ip_src_ip:
        filter_action:
        filter_application:
        filter_location:
        filter_log:
        filter_log_packet:
        filter_name:
        filter_os:
        filter_protocol:
        filter_quarantine:
        filter_quarantine_expiry:
        filter_quarantine_log:
        filter_severity:
        filter_status:
        override_action:
        override_log:
        override_log_packet:
        override_quarantine:
        override_quarantine_expiry:
        override_quarantine_log:
        override_rule_id:
        override_status:
        override_exempt_ip_dst_ip:
        override_exempt_ip_src_ip:
    
        list_overrides = ['entries', 'filter', 'override']
    
            override_data = list()
    
                override_data = module.params[list_variable]
    
                pass
    
    
                    del paramgram[list_variable]
                    paramgram[list_variable] = override_data
    
                pass



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

