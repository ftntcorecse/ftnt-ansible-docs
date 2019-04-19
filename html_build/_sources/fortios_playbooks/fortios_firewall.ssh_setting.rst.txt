============================
fortios_firewall.ssh_setting
============================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SSH proxy settings.
        fortios_firewall.ssh_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ssh_setting:
            caname: "<your_own_value> (source firewall.ssh.local-ca.name)"
            host-trusted-checking: "enable"
            hostkey-dsa1024: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ecdsa256: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ecdsa384: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ecdsa521: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ed25519: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-rsa2048: "myhostname (source firewall.ssh.local-key.name)"
            untrusted-caname: "<your_own_value> (source firewall.ssh.local-ca.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/firewall.ssh/fortios_firewall.ssh_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: SSH proxy settings.
        fortios_firewall.ssh_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ssh_setting:
            caname: "<your_own_value> (source firewall.ssh.local-ca.name)"
            host-trusted-checking: "enable"
            hostkey-dsa1024: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ecdsa256: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ecdsa384: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ecdsa521: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-ed25519: "myhostname (source firewall.ssh.local-key.name)"
            hostkey-rsa2048: "myhostname (source firewall.ssh.local-key.name)"
            untrusted-caname: "<your_own_value> (source firewall.ssh.local-ca.name)"




