==========
faz_device
==========


Metadata
--------




**Name:** faz_device

**Description:** Add or remove a device or list of devices to FortiAnalyzer Device Manager


**Author(s):** Luke Weighall (@lweighall)

**Ansible Version Added/Required:** 2.6

**Dev Status:** No Data Exists. Contact DevOps Team.

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


