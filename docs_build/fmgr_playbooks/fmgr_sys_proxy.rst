==============
fmgr_sys_proxy
==============


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: Proxy FOS requests via FMG
      hosts: FortiManager
      connection: local
      gather_facts: False
    
      tasks:
    
        - name: Get upgrade path for FGT1
          fmgr_provision:
            adom: "root"
            action: "get"
            resource: "/api/v2/monitor/system/firmware/upgrade-paths?vdom=root"
            target: ["/adom/root/device/FGT1"]
        - name: Upgrade firmware of FGT1
          fmgr_provision:
            adom: "root"
            action: "post"
            payload: {source: upload, file_content: b64_encoded_string, file_name: file_name}
            resource: "/api/v2/monitor/system/firmware/upgrade?vdom=vdom"
            target: ["/adom/root/device/FGT1"]
    



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

