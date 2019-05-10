===============
fsm_credentials
===============


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: ADD AN SSH CREDENTIAL
      fsm_credentials:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        cred_username: "fortinet"
        cred_password: "fortinet123!"
        access_protocol: "ssh"
        friendly_name: "AnsibleTestSSHCred"
        mode: "add"
        
    - name: ADD AN SSH CREDENTIAL FOR ELEVATED DEVICE
      fsm_credentials:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        cred_username: "fortinet"
        cred_password: "fortinet123!"
        super_username: "fortinet_super"
        super_password: "fortinet321!"
        access_protocol: "ssh"
        friendly_name: "AnsibleTestCiscoCred"
        mode: "add"
        ip_range: "10.0.254.1-10.0.254.255"
        
    - name: ADD AN VM_SDK CREDENTIAL
      fsm_credentials:
        host: "10.0.0.15"
        username: "super/api_user"
        password: "Fortinet!1"
        ignore_ssl_errors: "enable"
        cred_username: "fortinet"
        cred_password: "fortinet123!"
        access_protocol: "vm_sdk"
        friendly_name: "AnsibleTestVMSDKCred"
        mode: "add"
    
    - name: MSP UPDATE AN SSH CREDENTIAL
      fsm_credentials:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        cred_username: "fortinet"
        cred_password: "fortinet123!123"
        access_protocol: "ssh"
        description: "AnsibleTestSSHCredUPDATE"
        mode: "update"
        friendly_name: "AnsibleTestSSHCred"
        ip_range: "10.7.220.100"
    



Playbook File Examples
----------------------


fsm_add_access_methods.yml
++++++++++++++++++++++++++

.. code-block:: yaml



    - name: ADD ACCESS METHODS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
      - name: ADD AN SSH CREDENTIAL FROM FILE
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          input_xml_file: "creds2.xml"
          mode: "add"
    
      - name: ADD AN VM_SDK CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet"
          cred_password: "fortinet123!"
          access_protocol: "vm_sdk"
          friendly_name: "AnsibleTestVMSDKCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN SSH CREDENTIAL FOR ELEVATED DEVICE
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet"
          cred_password: "fortinet123!"
          super_password: "fortinet321!"
          access_protocol: "ssh"
          friendly_name: "AnsibleTestCiscoCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN FTP CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_ftp"
          cred_password: "fortinet123!"
          access_protocol: "ftp"
          friendly_name: "AnsibleTestFTPCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN FTP OVER SLL CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_ftp"
          cred_password: "fortinet123!"
          access_protocol: "ftp_over_ssl"
          friendly_name: "AnsibleTestFTPSSLCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN IMAP CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_imap"
          cred_password: "fortinet123!"
          access_protocol: "imap"
          friendly_name: "AnsibleTestIMAPCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
    
      - name: ADD AN IMAP OVER SSL CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_imapssl"
          cred_password: "fortinet123!"
          access_protocol: "imap_over_ssl"
          friendly_name: "AnsibleTestIMAPSSLCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN JDBC CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_jdbc"
          cred_password: "fortinet123!"
          access_protocol: "jdbc"
          friendly_name: "AnsibleTestJDBCCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN JMX CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_jmx"
          cred_password: "fortinet123!"
          access_protocol: "jmx"
          friendly_name: "AnsibleTestJMXCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN POP3 CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_pop3"
          cred_password: "fortinet123!"
          access_protocol: "pop3"
          friendly_name: "AnsibleTestPOP3Cred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN POP3 OVER SSL CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_pop3ssl"
          cred_password: "fortinet123!"
          access_protocol: "pop3_over_ssl"
          friendly_name: "AnsibleTestPOP3SSLCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN smtp CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_smtp"
          cred_password: "fortinet123!"
          access_protocol: "smtp"
          friendly_name: "AnsibleTestSMTPCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN smtp_over_ssl CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_smtp_over_ssl"
          cred_password: "fortinet123!"
          access_protocol: "smtp_over_ssl"
          friendly_name: "AnsibleTestsmtp_over_sslCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN smtp_over_tls CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_smtp_over_tls"
          cred_password: "fortinet123!"
          access_protocol: "smtp_over_tls"
          friendly_name: "AnsibleTestsmtp_over_tlsCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN FTP CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_ftp"
          cred_password: "fortinet123!"
          access_protocol: "ftp"
          friendly_name: "AnsibleTestFTPCred"
          description: "Created by api_user, and Ansible."
          mode: "add"
    
      - name: ADD AN telnet CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet_telnet"
          cred_password: "fortinet123!"
          access_protocol: "telnet"
          friendly_name: "AnsibleTesttelnetred"
          description: "Created by api_user, and Ansible."
          mode: "add"


fsm_msp_update_access_methods.yml
+++++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: MSP UPDATE ACCESS METHODS
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
      - name: MSP UPDATE AN SSH CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet"
          cred_password: "fortinet123!123"
          access_protocol: "ssh"
          description: "AnsibleTestSSHCredUPDATE"
          mode: "update"
          friendly_name: "AnsibleTestSSHCred"
          ip_range: "10.7.220.100"
    
      - name: MSP UPDATE AN SSH CREDENTIAL TEST ORG
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "adfs/api_user"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet"
          cred_password: "fortinet123!123"
          access_protocol: "ssh"
          description: "AnsibleTestSSHCredUPDATE"
          mode: "update"
          friendly_name: "AnsibleTestSSHCred"
          ip_range: "10.7.220.100"


fsm_get_access_methods.yml
++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET ACCESS METHODS
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
      - name: GET ALL CREDENTIALS
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          mode: "get"


creds2.xml
++++++++++

.. code-block:: xml

           <accessConfigs>
        <accessMethods>
            <accessMethod>
                <name>AnsibleTestSSHCred</name>
                <accessProtocol>SSH</accessProtocol>
                <description/>
                <pwdType>Manual</pwdType>
                <baseDN/>
                <pullInterval>5</pullInterval>
                <credential>
                    <password>fortinet</password>
                    <principal>fortinet</principal>
                    <suPassword/>
                </credential>
                <deviceType>
                    <model>Generic</model>
                    <vendor>Generic</vendor>
                    <version>ANY</version>
                </deviceType>
            </accessMethod>
        </accessMethods>
        <ipAccessMappings>
            <ipAccessMapping>
                <ipRange>10.0.0.5</ipRange>
            </ipAccessMapping>
        </ipAccessMappings>
    </accessConfigs>

fsm_msp_get_access_methods.yml
++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: MSP GET ACCESS METHODS
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
      - name: MSP GET ALL CREDENTIALS
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          mode: "get"


creds3_output_msp_dual_collector.xml
++++++++++++++++++++++++++++++++++++

.. code-block:: xml

           <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <accessConfigs>
        <accessMethods>
            <accessMethod creationTime="1557441071533" custId="2056" entityVersion="0" id="2305600"
                          lastModified="1557441071533" ownerId="500151" xmlId="AccessMethod@2305600">
                <accessProtocol>FTP</accessProtocol>
                <baseDN/>
                <caAddress>false</caAddress>
                <description/>
                <name>test123</name>
                <port>21</port>
                <pullInterval>5</pullInterval>
                <pwdType>Manual</pwdType>
                <useLDAP>false</useLDAP>
                <credential creationTime="1557441071534" custId="2056" entityVersion="0" id="2305650"
                            lastModified="1557441071534" ownerId="0" xmlId="Credential@2305650">
                    <password>AES$83173CC2D07E45B1548CD9F0F4592C2B</password>
                    <principal>test</principal>
                    <suPassword/>
                </credential>
                <deviceType creationTime="1555436989024" custId="0" entityVersion="1" id="794651"
                            lastModified="1556344621972" ownerId="0" xmlId="DeviceType@794651">
                    <type>Appliance</type>
                    <eventParsed>false</eventParsed>
                    <jobWeight>10</jobWeight>
                    <model>Generic</model>
                    <objectGroup>PH_SYS_DEVICE_GENERIC</objectGroup>
                    <priority>0</priority>
                    <sysDefined>true</sysDefined>
                    <vendor>Generic</vendor>
                    <version>ANY</version>
                </deviceType>
            </accessMethod>
        </accessMethods>
        <ipAccessMappings>
            <ipAccessMapping creationTime="1557441080093" custId="2056" entityVersion="0" id="2305700"
                             lastModified="1557441080093" ownerId="0" xmlId="IpAccessMapping@2305700">
                <collectorId>10034</collectorId>
                <accessMethodId>2305600</accessMethodId>
                <ipRange>10.1.1.1</ipRange>
            </ipAccessMapping>
            <ipAccessMapping creationTime="1557441088108" custId="2056" entityVersion="0" id="2305701"
                             lastModified="1557441088108" ownerId="0" xmlId="IpAccessMapping@2305701">
                <collectorId>10035</collectorId>
                <accessMethodId>2305600</accessMethodId>
                <ipRange>10.0.0.2</ipRange>
            </ipAccessMapping>
        </ipAccessMappings>
    </accessConfigs>


creds.xml
+++++++++

.. code-block:: xml

           <accessConfigs>
        <accessMethods>
            <accessMethod>
                <accessProtocol>MS_WMI</accessProtocol>
                <baseDN/>
                <description/>
                <name>MS-WMI-Domain_ABC</name>
                <port/>
                <pwdType>Manual</pwdType>
                <pullInterval>5</pullInterval>
                <credential>
                    <password>abc</password>
                    <principal>ABC/user123</principal>
                    <suPassword/>
                </credential>
                <deviceType >
                    <accessProtocols>MS_RPC,MS_WMI,LDAP</accessProtocols>
                    <model>Windows</model>
                    <vendor>Microsoft</vendor>
                    <version>ANY</version>
                </deviceType>
            </accessMethod>
        </accessMethods>
        <ipAccessMappings>
            <ipAccessMapping>
                <ipRange>1.1.1.1</ipRange>
            </ipAccessMapping>
        </ipAccessMappings>
    </accessConfigs>

fsm_msp_add_access_methods.yml
++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: MSP ADD ACCESS METHODS
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
      - name: MSP ADD AN SSH CREDENTIAL
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet"
          cred_password: "fortinet123!"
          access_protocol: "ssh"
          description: "AnsibleTestSSHCred"
          mode: "add"
          friendly_name: "AnsibleTestSSHCred"
    
      - name: MSP ADD AN SSH CREDENTIAL TEST ORG
        fsm_credentials:
          host: "{{ inventory_hostname }}"
          username: "adfs/api_user"
          password: "{{ password }}"
          ignore_ssl_errors: "enable"
          cred_username: "fortinet"
          cred_password: "fortinet123!"
          access_protocol: "ssh"
          description: "AnsibleTestSSHCred"
          mode: "add"
          friendly_name: "AnsibleTestSSHCred"




