==========
faz_device
==========


Metadata
--------




**Name:** faz_device

**Description:** ['Add or remove a device or list of devices to FortiAnalyzer Device Manager']

**Author(s):** Luke Weighall (@lweighall)

**Ansible Version Added/Required:** 2.6

**Dev Status:** Not currently tracked. Likelihood is this is a private module for a one-off need that hasn't been finalized for Ansible testing yet.

Parameters
----------

adom
++++

- Description: The ADOM the configuration should belong to.

  

- Required: True

- default: root

device_action
+++++++++++++

- Description: Specify add device operations, or leave blank to add a real device from scratch

  

- Required: False

- default: add_model

- choices: ['add_model', 'promote_unreg']

device_ip
+++++++++

- Description: The IP of the device being added to FortiManager.

  

- Required: False

device_password
+++++++++++++++

- Description: The password of the device being added to FortiManager.

  

- Required: False

device_serial
+++++++++++++

- Description: The serial number of the device being added to FortiManager.

  

- Required: False

device_unique_name
++++++++++++++++++

- Description: The desired "friendly" name of the device being added to FortiManager.

  

- Required: False

device_username
+++++++++++++++

- Description: The username of the device being added to FortiManager.

  

- Required: False

faz_quota
+++++++++

- Description: Specifies the quota for the device in FAZ

  

- Required: False

host
++++

- Description: The FortiManager's Address.

  

- Required: True

mgmt_mode
+++++++++

- Description: Management Mode of the device you are adding.

  

- Required: True

- choices: ['unreg', 'fmg', 'faz', 'fmgfaz']

os_minor_vers
+++++++++++++

- Description: Minor OS rev of the device

  

- Required: True

os_type
+++++++

- Description: The os type of the device being added (default 0).

  

- Required: True

- choices: ['unknown', 'fos', 'fsw', 'foc', 'fml', 'faz', 'fwb', 'fch', 'fct', 'log', 'fmg', 'fsa', 'fdd', 'fac']

os_ver
++++++

- Description: Major OS rev of the device

  

- Required: True

- choices: ['unknown', '0.0', '1.0', '2.0', '3.0', '4.0', '5.0', '6.0']

password
++++++++

- Description: The password associated with the username account.

  

- Required: False

platform_str
++++++++++++

- Description: Required for determine the platform for VM platforms. ie FortiGate-VM64

  

- Required: False

state
+++++

- Description: The desired state of the specified object.

  absent will delete the object if it exists.

  present will create the configuration if needed.

  

- Required: False

- default: present

- choices: ['absent', 'present']

username
++++++++

- Description: The username used to authenticate with the FortiManager.

  

- Required: False




Functions
---------




- faz_add_device

 .. code-block:: python

    def faz_add_device(faz, paramgram):
        """
        This method is used to add devices to the faz or delete them
        """
    
        datagram = {
            "adom": paramgram["adom"],
            "device": {"adm_usr": paramgram["device_username"], "adm_pass": paramgram["device_password"],
                       "ip": paramgram["ip"], "name": paramgram["device_unique_name"],
                       "mgmt_mode": paramgram["mgmt_mode"], "os_type": paramgram["os_type"],
                       "mr": paramgram["os_minor_vers"]}
        }
    
        if paramgram["platform_str"] is not None:
            datagram["device"]["platform_str"] = paramgram["platform_str"]
    
        if paramgram["sn"] is not None:
            datagram["device"]["sn"] = paramgram["sn"]
    
        if paramgram["device_action"] is not None:
            datagram["device"]["device_action"] = paramgram["device_action"]
    
        if paramgram["faz.quota"] is not None:
            datagram["device"]["faz.quota"] = paramgram["faz.quota"]
    
    
        url = '/dvm/cmd/add/device/'
        response = faz.execute(url, datagram)
        return response
    
    

- faz_delete_device

 .. code-block:: python

    def faz_delete_device(faz, paramgram):
        """
        This method deletes a device from the FMGR
        """
        datagram = {
            "adom": paramgram["adom"],
            "device": paramgram["device_unique_name"],
        }
    
        url = '/dvm/cmd/del/device/'
        response = faz.execute(url, datagram)
        return response
    
    

- faz_get_unknown_devices

 .. code-block:: python

    def faz_get_unknown_devices(faz):
        '''
        This method gets devices with an unknown management type field
        '''
    
        filter = ["mgmt_mode", "==", "0"]
    
        datagram = {
            "filter": filter
        }
    
        url = "/dvmdb/device"
        response = faz.get(url, datagram)
    
        return response
    
    

- faz_approve_unregistered_device_by_ip

 .. code-block:: python

    def faz_approve_unregistered_device_by_ip(faz, paramgram):
    
        # TRY TO FIND DETAILS ON THIS UNREGISTERED DEVICE
        unknown_devices = faz_get_unknown_devices(faz)
        target_device = None
        if unknown_devices[0] == 0:
            for device in unknown_devices[1]:
                if device["ip"] == paramgram["ip"]:
                    target_device = device
        else:
            return "No devices are waiting to be registered!"
    
        # now that we have the target device details...fill out the datagram and make the call to promote it
        if target_device is not None:
            target_device_paramgram = {
                "adom": paramgram["adom"],
                "ip": target_device["ip"],
                "device_username": paramgram["device_username"],
                "device_password": paramgram["device_password"],
                "device_unique_name": paramgram["device_unique_name"],
                "sn": target_device["sn"],
                "os_type": target_device["os_type"],
                "mgmt_mode": paramgram["mgmt_mode"],
                "os_minor_vers": target_device["mr"],
                "os_ver": target_device["os_ver"],
                "platform_str": target_device["platform_str"],
                "faz.quota": target_device["faz.quota"],
                "device_action": paramgram["device_action"]
            }
    
            add_device = faz_add_device(faz, target_device_paramgram)
            return add_device
    
    
        return str("Couldn't find the desired device with ip: " + str(paramgram["device_ip"]))
    
    

- faz_approve_unregistered_device_by_name

 .. code-block:: python

    def faz_approve_unregistered_device_by_name(faz, paramgram):
    
        # TRY TO FIND DETAILS ON THIS UNREGISTERED DEVICE
        unknown_devices = faz_get_unknown_devices(faz)
        target_device = None
        if unknown_devices[0] == 0:
            for device in unknown_devices[1]:
                if device["name"] == paramgram["device_unique_name"]:
                    target_device = device
        else:
            return "No devices are waiting to be registered!"
    
        # now that we have the target device details...fill out the datagram and make the call to promote it
        if target_device is not None:
            target_device_paramgram = {
                "adom": paramgram["adom"],
                "ip": target_device["ip"],
                "device_username": paramgram["device_username"],
                "device_password": paramgram["device_password"],
                "device_unique_name": paramgram["device_unique_name"],
                "sn": target_device["sn"],
                "os_type": target_device["os_type"],
                "mgmt_mode": paramgram["mgmt_mode"],
                "os_minor_vers": target_device["mr"],
                "os_ver": target_device["os_ver"],
                "platform_str": target_device["platform_str"],
                "faz.quota": target_device["faz.quota"],
                "device_action": paramgram["device_action"]
            }
    
            add_device = faz_add_device(faz, target_device_paramgram)
            return add_device
    
    
        return str("Couldn't find the desired device with name: " + str(paramgram["device_unique_name"]))
    
    

- main

 .. code-block:: python

    def main():
        argument_spec = dict(
            adom=dict(required=False, type="str", default="root"),
            host=dict(required=True, type="str"),
            username=dict(fallback=(env_fallback, ["ANSIBLE_NET_USERNAME"])),
            password=dict(fallback=(env_fallback, ["ANSIBLE_NET_PASSWORD"]), no_log=True),
            state=dict(choices=["absent", "present"], type="str", default="present"),
    
            device_ip=dict(required=False, type="str"),
            device_username=dict(required=False, type="str"),
            device_password=dict(required=False, type="str", no_log=True),
            device_unique_name=dict(required=True, type="str"),
            device_serial=dict(required=False, type="str"),
    
            os_type=dict(required=False, type="str"),
            mgmt_mode=dict(required=False, type="str"),
            os_minor_vers=dict(required=False, type="str"),
            os_ver=dict(required=False, type="str"),
            platform_str=dict(required=False, type="str"),
            device_action=dict(required=False, type="str", default="add_model"),
            faz_quota=dict(required=False, type="str")
        )
    
        module = AnsibleModule(argument_spec, supports_check_mode=True,)
    
        # validate required arguments are passed; not used in argument_spec to allow params to be called from provider
        # check if params are set
        if module.params["host"] is None or module.params["username"] is None:
            module.fail_json(msg="Host and username are required for connection")
    
        # CHECK IF LOGIN FAILED
        faz = AnsibleFortiManager(module, module.params["host"], module.params["username"], module.params["password"])
        response = faz.login()
    
        if response[0] != 0:
            module.fail_json(msg="Connection to FortiAnalyzer Failed")
        else:
            # START SESSION LOGIC
            paramgram = {
                "adom": module.params["adom"],
                "ip": module.params["device_ip"],
                "device_username": module.params["device_username"],
                "device_password": module.params["device_password"],
                "device_unique_name": module.params["device_unique_name"],
                "sn": module.params["device_serial"],
                "os_type": module.params["os_type"],
                "mgmt_mode": module.params["mgmt_mode"],
                "os_minor_vers": module.params["os_minor_vers"],
                "os_ver": module.params["os_ver"],
                "platform_str": module.params["platform_str"],
                "faz.quota": module.params["faz_quota"],
                "device_action": module.params["device_action"]
            }
    
            if module.params["state"] == "present":
                if paramgram["device_action"] == "promote_unreg":
                    if paramgram["ip"] is not None:
                        results = faz_approve_unregistered_device_by_ip(faz, paramgram)
                    elif paramgram["device_unique_name"] is not None:
                        results = faz_approve_unregistered_device_by_name(faz, paramgram)
                else:
                    results = faz_add_device(faz, paramgram)
                if results[0] not in [0, -20010]:
                    module.fail_json(msg="ADDING Device Failed", **results[1])
    
    
            if module.params["state"] == "absent":
                results = faz_delete_device(faz, paramgram)
                if results[0] not in [0]:
                    module.fail_json(msg="DELETING Device Failed", **results[1])
        # logout
        faz.logout()
        # results is returned as a tuple
        return module.exit_json(**results[1])
    
    



Module Source Code
------------------

.. code-block:: python

    #!/usr/bin/python
    #
    # This file is part of Ansible
    #
    # Ansible is free software: you can redistribute it and/or modify
    # it under the terms of the GNU General Public License as published by
    # the Free Software Foundation, either version 3 of the License, or
    # (at your option) any later version.
    #
    # Ansible is distributed in the hope that it will be useful,
    # but WITHOUT ANY WARRANTY; without even the implied warranty of
    # MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    # GNU General Public License for more details.
    #
    # You should have received a copy of the GNU General Public License
    # along with Ansible.  If not, see <http://www.gnu.org/licenses/>.
    #
    
    from __future__ import absolute_import, division, print_function
    __metaclass__ = type
    
    ANSIBLE_METADATA = {
        "metadata_version": "1.1",
        "status": ["preview"],
        "supported_by": "community"
    }
    
    DOCUMENTATION = '''
    ---
    module: faz_device
    version_added: "2.6"
    author: Luke Weighall (@lweighall)
    short_description: Add or remove device
    description:
      - Add or remove a device or list of devices to FortiAnalyzer Device Manager
    
    options:
      adom:
        description:
          - The ADOM the configuration should belong to.
        required: true
        default: root
      host:
        description:
          - The FortiManager's Address.
        required: true
      username:
        description:
          - The username used to authenticate with the FortiManager.
        required: false
      password:
        description:
          - The password associated with the username account.
        required: false
      state:
        description:
          - The desired state of the specified object.
          - absent will delete the object if it exists.
          - present will create the configuration if needed.
        required: false
        default: present
        choices: ["absent", "present"]
    
      device_username:
        description:
          - The username of the device being added to FortiManager.
        required: false
      device_password:
        description:
          - The password of the device being added to FortiManager.
        required: false
      device_ip:
        description:
          - The IP of the device being added to FortiManager.
        required: false
      device_unique_name:
        description:
          - The desired "friendly" name of the device being added to FortiManager.
        required: false
      device_serial:
        description:
          - The serial number of the device being added to FortiManager.
        required: false
        
      os_type:
        description:
          - The os type of the device being added (default 0).
        required: true
        choices: ["unknown", "fos", "fsw", "foc", "fml", "faz", "fwb", "fch", "fct", "log", "fmg", "fsa", "fdd", "fac"]
      mgmt_mode:
        description:
          - Management Mode of the device you are adding.
        choices: ["unreg", "fmg", "faz", "fmgfaz"]
        required: true
      os_minor_vers:
        description:
          - Minor OS rev of the device  
        required: true
      os_ver:
        description:
          - Major OS rev of the device
        required: true
        choices: ["unknown", "0.0", "1.0", "2.0", "3.0", "4.0", "5.0", "6.0"] 
      platform_str:
        description:
          - Required for determine the platform for VM platforms. ie FortiGate-VM64 
        required: false
      device_action:
        description:
          - Specify add device operations, or leave blank to add a real device from scratch
        required: false
        choices: ["add_model", "promote_unreg"]
        default: "add_model"
      faz_quota:
        description:
          - Specifies the quota for the device in FAZ
        required: False
        
    '''
    
    
    EXAMPLES = '''
    - name: DISCOVER AND ADD DEVICE A PHYSICAL FORTIGATE
      faz_device:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.201"
        device_unique_name: "FGT1"
        device_serial: "FGVM000000117994"
        state: "present"
        mgmt_mode: "faz"
        os_type: "fos"
        os_ver: "5.0"
        minor_rev: 6
        
    
    - name: DISCOVER AND ADD DEVICE A VIRTUAL FORTIGATE
      faz_device:
        host: "{{inventory_hostname}}"
        username: "{{ username }}"
        password: "{{ password }}"
        adom: "root"
        device_username: "admin"
        device_password: "admin"
        device_ip: "10.10.24.202"
        device_unique_name: "FGT2"
        mgmt_mode: "faz"
        os_type: "fos"
        os_ver: "5.0"
        minor_rev: 6
        state: "present"
        platform_str: "FortiGate-VM64"
    '''
    
    RETURN = """
    api_result:
      description: full API response, includes status code and message
      returned: always
      type: string
    """
    
    from ansible.module_utils.basic import AnsibleModule, env_fallback
    from ansible.module_utils.network.fortimanager.fortimanager import AnsibleFortiManager
    
    
    
    # check for pyFMG lib
    try:
        from pyFMG.fortimgr import FortiManager
        HAS_PYFMGR = True
    except ImportError:
        HAS_PYFMGR = False
    
    #import pydevd
    
    def faz_add_device(faz, paramgram):
        """
        This method is used to add devices to the faz or delete them
        """
    
        datagram = {
            "adom": paramgram["adom"],
            "device": {"adm_usr": paramgram["device_username"], "adm_pass": paramgram["device_password"],
                       "ip": paramgram["ip"], "name": paramgram["device_unique_name"],
                       "mgmt_mode": paramgram["mgmt_mode"], "os_type": paramgram["os_type"],
                       "mr": paramgram["os_minor_vers"]}
        }
    
        if paramgram["platform_str"] is not None:
            datagram["device"]["platform_str"] = paramgram["platform_str"]
    
        if paramgram["sn"] is not None:
            datagram["device"]["sn"] = paramgram["sn"]
    
        if paramgram["device_action"] is not None:
            datagram["device"]["device_action"] = paramgram["device_action"]
    
        if paramgram["faz.quota"] is not None:
            datagram["device"]["faz.quota"] = paramgram["faz.quota"]
    
    
        url = '/dvm/cmd/add/device/'
        response = faz.execute(url, datagram)
        return response
    
    
    def faz_delete_device(faz, paramgram):
        """
        This method deletes a device from the FMGR
        """
        datagram = {
            "adom": paramgram["adom"],
            "device": paramgram["device_unique_name"],
        }
    
        url = '/dvm/cmd/del/device/'
        response = faz.execute(url, datagram)
        return response
    
    
    def faz_get_unknown_devices(faz):
        '''
        This method gets devices with an unknown management type field
        '''
    
        filter = ["mgmt_mode", "==", "0"]
    
        datagram = {
            "filter": filter
        }
    
        url = "/dvmdb/device"
        response = faz.get(url, datagram)
    
        return response
    
    
    def faz_approve_unregistered_device_by_ip(faz, paramgram):
    
        # TRY TO FIND DETAILS ON THIS UNREGISTERED DEVICE
        unknown_devices = faz_get_unknown_devices(faz)
        target_device = None
        if unknown_devices[0] == 0:
            for device in unknown_devices[1]:
                if device["ip"] == paramgram["ip"]:
                    target_device = device
        else:
            return "No devices are waiting to be registered!"
    
        # now that we have the target device details...fill out the datagram and make the call to promote it
        if target_device is not None:
            target_device_paramgram = {
                "adom": paramgram["adom"],
                "ip": target_device["ip"],
                "device_username": paramgram["device_username"],
                "device_password": paramgram["device_password"],
                "device_unique_name": paramgram["device_unique_name"],
                "sn": target_device["sn"],
                "os_type": target_device["os_type"],
                "mgmt_mode": paramgram["mgmt_mode"],
                "os_minor_vers": target_device["mr"],
                "os_ver": target_device["os_ver"],
                "platform_str": target_device["platform_str"],
                "faz.quota": target_device["faz.quota"],
                "device_action": paramgram["device_action"]
            }
    
            add_device = faz_add_device(faz, target_device_paramgram)
            return add_device
    
    
        return str("Couldn't find the desired device with ip: " + str(paramgram["device_ip"]))
    
    
    def faz_approve_unregistered_device_by_name(faz, paramgram):
    
        # TRY TO FIND DETAILS ON THIS UNREGISTERED DEVICE
        unknown_devices = faz_get_unknown_devices(faz)
        target_device = None
        if unknown_devices[0] == 0:
            for device in unknown_devices[1]:
                if device["name"] == paramgram["device_unique_name"]:
                    target_device = device
        else:
            return "No devices are waiting to be registered!"
    
        # now that we have the target device details...fill out the datagram and make the call to promote it
        if target_device is not None:
            target_device_paramgram = {
                "adom": paramgram["adom"],
                "ip": target_device["ip"],
                "device_username": paramgram["device_username"],
                "device_password": paramgram["device_password"],
                "device_unique_name": paramgram["device_unique_name"],
                "sn": target_device["sn"],
                "os_type": target_device["os_type"],
                "mgmt_mode": paramgram["mgmt_mode"],
                "os_minor_vers": target_device["mr"],
                "os_ver": target_device["os_ver"],
                "platform_str": target_device["platform_str"],
                "faz.quota": target_device["faz.quota"],
                "device_action": paramgram["device_action"]
            }
    
            add_device = faz_add_device(faz, target_device_paramgram)
            return add_device
    
    
        return str("Couldn't find the desired device with name: " + str(paramgram["device_unique_name"]))
    
    
    def main():
        argument_spec = dict(
            adom=dict(required=False, type="str", default="root"),
            host=dict(required=True, type="str"),
            username=dict(fallback=(env_fallback, ["ANSIBLE_NET_USERNAME"])),
            password=dict(fallback=(env_fallback, ["ANSIBLE_NET_PASSWORD"]), no_log=True),
            state=dict(choices=["absent", "present"], type="str", default="present"),
    
            device_ip=dict(required=False, type="str"),
            device_username=dict(required=False, type="str"),
            device_password=dict(required=False, type="str", no_log=True),
            device_unique_name=dict(required=True, type="str"),
            device_serial=dict(required=False, type="str"),
    
            os_type=dict(required=False, type="str"),
            mgmt_mode=dict(required=False, type="str"),
            os_minor_vers=dict(required=False, type="str"),
            os_ver=dict(required=False, type="str"),
            platform_str=dict(required=False, type="str"),
            device_action=dict(required=False, type="str", default="add_model"),
            faz_quota=dict(required=False, type="str")
        )
    
        module = AnsibleModule(argument_spec, supports_check_mode=True,)
    
        # validate required arguments are passed; not used in argument_spec to allow params to be called from provider
        # check if params are set
        if module.params["host"] is None or module.params["username"] is None:
            module.fail_json(msg="Host and username are required for connection")
    
        # CHECK IF LOGIN FAILED
        faz = AnsibleFortiManager(module, module.params["host"], module.params["username"], module.params["password"])
        response = faz.login()
    
        if response[0] != 0:
            module.fail_json(msg="Connection to FortiAnalyzer Failed")
        else:
            # START SESSION LOGIC
            paramgram = {
                "adom": module.params["adom"],
                "ip": module.params["device_ip"],
                "device_username": module.params["device_username"],
                "device_password": module.params["device_password"],
                "device_unique_name": module.params["device_unique_name"],
                "sn": module.params["device_serial"],
                "os_type": module.params["os_type"],
                "mgmt_mode": module.params["mgmt_mode"],
                "os_minor_vers": module.params["os_minor_vers"],
                "os_ver": module.params["os_ver"],
                "platform_str": module.params["platform_str"],
                "faz.quota": module.params["faz_quota"],
                "device_action": module.params["device_action"]
            }
    
            if module.params["state"] == "present":
                if paramgram["device_action"] == "promote_unreg":
                    if paramgram["ip"] is not None:
                        results = faz_approve_unregistered_device_by_ip(faz, paramgram)
                    elif paramgram["device_unique_name"] is not None:
                        results = faz_approve_unregistered_device_by_name(faz, paramgram)
                else:
                    results = faz_add_device(faz, paramgram)
                if results[0] not in [0, -20010]:
                    module.fail_json(msg="ADDING Device Failed", **results[1])
    
    
            if module.params["state"] == "absent":
                results = faz_delete_device(faz, paramgram)
                if results[0] not in [0]:
                    module.fail_json(msg="DELETING Device Failed", **results[1])
        # logout
        faz.logout()
        # results is returned as a tuple
        return module.exit_json(**results[1])
    
    
    if __name__ == "__main__":
        main()



RAW HTML JSON Guide
-------------------

.. raw:: html

    <html>
    <body>
        <h2 id='add_device'>add/device (command)</h2><p>Add a device to the Device Manager database.</p><p>Supported methods: <a href="dvmcmd-methods.htm#exec">exec</a>
        </p>
        <h6>Object URL:</h6>
        <table>
            <tr>
                <td class="table_col_name">Command object</td>
                <td class="table_col_desc">/dvm/cmd/add/device<br/>
                </td>
            </tr>
        </table>
        <table class='param_table'>
            <col class='table_hdr_name'/>
            <col class='table_hdr_desc'/>
            <thead>
                <tr>
                    <th class='table_hdr_name'>Attribute List</th>
                    <th class='table_hdr_desc'>Descriptions</th>
                </tr>
            </thead>
            <tbody>
                <tr class="odd_row">
                    <td class="table_col_name">adom</td>
                    <td class="table_col_desc">
                        <i>datasource</i>, refer to <a href="dvmdb-objects.htm#adom">adom object</a> (36 bytes)<br/>Name or ID of the ADOM where the command is to be executed on.</td>
                </tr>
                <tr class="even_row">
                    <td class="table_col_name">device</td>
                    <td class="table_col_desc">
                        <i>object</i>
                        <br/>Device object to be added. Refer to <i>device action</i> attribute to select different type of add operation.<table>
        <tr class="odd_row">
            <td class="table_col_name">adm_pass</td>
            <td class="table_col_desc">
                <i>password</i> (128 bytes)<br/>
                <i>add real and promote device</i>.</td>
        </tr>
        <tr class="even_row">
            <td class="table_col_name">adm_usr</td>
            <td class="table_col_desc">
                <i>string</i> (36 bytes)<br/>
                <i>add real and promote device</i>.</td>
        </tr>
        <tr class="odd_row">
            <td class="table_col_name">desc</td>
            <td class="table_col_desc">
                <i>string</i> (128 bytes)<br/>
                <i>available for all operations</i>.</td>
        </tr>
        <tr class="even_row">
            <td class="table_col_name">device action</td>
            <td class="table_col_desc">
                <i>string</i>
                <br/>Specify add device operations, or leave blank to add real device:<ul>
                    <li>"add_model" - add a model device.<li>"promote_unreg" - promote an unregistered device to be managed by FortiManager using information from database.</ul>
                    </td>
                </tr>
                <tr class="odd_row">
                    <td class="table_col_name">faz.quota</td>
                    <td class="table_col_desc">
                        <i>unsigned int32</i>
                        <br/>
                        <i>available for all operations</i>.</td>
                </tr>
                <tr class="even_row">
                    <td class="table_col_name">ip</td>
                    <td class="table_col_desc">
                        <i>string</i> (45 bytes)<br/>
                        <i>add real device only</i>. Add device will probe with this IP using the log in credential specified.</td>
                </tr>
                <tr class="odd_row">
                    <td class="table_col_name">meta fields</td>
                    <td class="table_col_desc">
                        <i>string</i>
                        <br/>
                        <i>add real and model device</i>.</td>
                </tr>
                <tr class="even_row">
                    <td class="table_col_name">mgmt_mode</td>
                    <td class="table_col_desc">
                        <i>option</i>
                        <br/>
                        <i>add real and model device</i>.<table>
                            <tr>
            <td class="table_col_name">&quot;unreg&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fmg&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;faz&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fmgfaz&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                        </table>
                    </td>
                </tr>
                <tr class="odd_row">
                    <td class="table_col_name">mr</td>
                    <td class="table_col_desc">
                        <i>int16</i>
                        <br/>
                        <i>add model device only</i>.</td>
                </tr>
                <tr class="even_row">
                    <td class="table_col_name">name</td>
                    <td class="table_col_desc">
                        <i>string</i> (36 bytes)<br/>
                        <i>required for all operations</i>. Unique name for the device.</td>
                </tr>
                <tr class="odd_row">
                    <td class="table_col_name">os_type</td>
                    <td class="table_col_desc">
                        <i>option</i>
                        <br/>
                        <i>add model device only</i>.<table>
                            <tr>
            <td class="table_col_name">&quot;unknown&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fos&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fsw&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;foc&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fml&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;faz&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fwb&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fch&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fct&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;log&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fmg&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fsa&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fdd&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;fac&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                        </table>
                    </td>
                </tr>
                <tr class="even_row">
                    <td class="table_col_name">os_ver</td>
                    <td class="table_col_desc">
                        <i>option</i>
                        <br/>
                        <i>add model device only</i>.<table>
                            <tr>
            <td class="table_col_name">&quot;unknown&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;0.0&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;1.0&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;2.0&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;3.0&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;4.0&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                            <tr>
            <td class="table_col_name">&quot;5.0&quot;</td>
            <td class="table_col_desc"/>
                            </tr>
                        </table>
                    </td>
                </tr>
                <tr class="odd_row">
                    <td class="table_col_name">patch</td>
                    <td class="table_col_desc">
                        <i>int16</i>
                        <br/>
                        <i>add model device only</i>.</td>
                </tr>
                <tr class="even_row">
                    <td class="table_col_name">platform_str</td>
                    <td class="table_col_desc">
                        <i>string</i> (32 bytes)<br/>
                        <i>add model device only</i>. Required for determine the platform for VM platforms.</td>
                </tr>
                <tr class="odd_row">
                    <td class="table_col_name">sn</td>
                    <td class="table_col_desc">
                        <i>string</i> (16 bytes)<br/>
                        <i>add model device only</i>. This attribute will be used to determine the device platform, except for VM platforms, where <i>platform_str</i> is also required.</td>
                </tr>
            </table>
        </td>
                        </tr>
                        <tr class="odd_row">
        <td class="table_col_name">flags</td>
        <td class="table_col_desc">
            <i>flags</i>
            <table>
                <tr>
                    <td class="table_col_name">&quot;none&quot;</td>
                    <td class="table_col_desc">[<i>Default value</i>]<br/>
                    </td>
                </tr>
                <tr>
                    <td class="table_col_name">&quot;create_task&quot;</td>
                    <td class="table_col_desc">Create a new task in task manager database.</td>
                </tr>
                <tr>
                    <td class="table_col_name">&quot;nonblocking&quot;</td>
                    <td class="table_col_desc">The API will return immediately in for non-blocking call. This flag will be set automatically when the adding, importing, updating, and deleting a list of devices.</td>
                </tr>
            </table>
        </td>
                        </tr>
                        <tr class="even_row">
        <td class="table_col_name">groups</td>
        <td class="table_col_desc">
            <i>datasource</i>, refer to <a href="dvmdb-objects.htm#group">group object</a>
        </td>
                        </tr>
                    </tbody>
                </table>
                <table class='param_table'>
                    <col class='table_hdr_name'/>
                    <col class='table_hdr_desc'/>
                    <thead>
                        <tr>
        <th class='table_hdr_name'>Response Data</th>
        <th class='table_hdr_desc'>Descriptions</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr class="odd_row">
        <td class="table_col_name">device</td>
        <td class="table_col_desc">
            <i>datasource</i>, refer to <a href="dvmdb-objects.htm#device">device object</a>
            <br/>Name or ID of the target device.<table/>
        </td>
                        </tr>
                        <tr class="even_row">
        <td class="table_col_name">pid</td>
        <td class="table_col_desc">
            <i>unsigned int32</i>
            <br/>When "nonblocking" flag is set, return the process ID for the command.</td>
                        </tr>
                        <tr class="odd_row">
        <td class="table_col_name">taskid</td>
        <td class="table_col_desc">
            <i>datasource</i>, refer to <a href="task-objects.htm#task">task</a>
            <br/>When "create_task" flag is set, return the ID of the task associated with the command.</td>
                        </tr>
                    </tbody>
    </table>    </body></html>

