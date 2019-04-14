================
fmgr_secprof_ips
================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_ips:
          name: "Ansible_IPS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_ips:
          name: "Ansible_IPS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          block_malicious_url: "enable"
          entries: [{severity: "high", action: "block", log-packet: "enable"}, {severity: "medium", action: "pass"}]



Playbook File Examples
----------------------


ips.yml
+++++++

.. code-block:: yaml


    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
    #  - name: DELETE Profile
    #    fmgr_secprof_ips:
    #      name: "Ansible_IPS_Profile"
    #      comment: "Created by Ansible Module TEST"
    #      mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_ips:
          name: "Ansible_IPS_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          block_malicious_url: "enable"
          entries: [{severity: "high", action: "block", log-packet: "enable"}, {severity: "medium", action: "pass"}]
    #      replacemsg_group: "test"
    
    #      replacemsg_group: [{admin: [{buffer: "buffer", format: "html", header: "http", msg-type: "test message"}],
    #
    #        alertmail: [{buffer: "buffer", format: "html", header: "http", msg-type: "test message"}],
    #        auth: [{buffer: "buffer", format: "text", header: "8bit", msg-type: "test message"}],
    #        comment: "Ansible",
    #        group-type: "utm",
    #        name: "replacement-message-ansible"
    #      }
    #      ]
    
    


ips2.yml
++++++++

.. code-block:: yaml


    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    #    - name: DELETE Profile
    #      fmgr_ips_sensor:
    #        name: "Ansible_IPS_Profile"
    #        comment: "Created by Ansible Module TEST"
    #        mode: "delete"
    
    
        - name: CREATE Profile
          fmgr_ips_sensor:
            name: "Ansible_IPS_Profile"
            comment: "Created by Ansible Module TEST"
            mode: "set"
            block_malicious_url: "enable"
    
            entries_action: "block"
            entries_severity: "high"
            entries_log: "enable"
            entries_status: "enable"
    
            entries: [{severity: "high", action: "block"}, {severity: "low", action: "pass"}]

fmgr_secprof_ips_run_all.sh
+++++++++++++++++++++++++++

.. code-block:: yaml
            #!/bin/bash
    ansible-playbook ips.yml -vvvv




