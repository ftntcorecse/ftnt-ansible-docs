====================
fortios_router_ripng
====================


Metadata
--------




**Name:** fortios_router_ripng

**Description:** This module is able to configure a FortiGate or FortiOS by allowing the user to configure router feature and ripng category. Examples includes all options and need to be adjusted to datasources before usage. Tested with FOS v6.0.2


**Author(s):** 

- Miguel Angel Munoz (github: @mamunozgonzalez)

- Nicolas Thomas (github: @thomnico)



**Ansible Version Added/Required:** 2.8

**Dev Status:** No Data Exists. Contact DevOps Team.

Parameters
----------

host
++++

- Description: FortiOS or FortiGate ip adress.

  

- Required: True

https
+++++

- Description: Indicates if the requests towards FortiGate must use HTTPS protocol

  

- default: False

password
++++++++

- Description: FortiOS or FortiGate password.

  

- default: 

router_ripng
++++++++++++

- Description: Configure RIPng.

  

- default: None

username
++++++++

- Description: FortiOS or FortiGate username.

  

- Required: True

vdom
++++

- Description: Virtual domain, among those defined previously. A vdom is a virtual instance of the FortiGate that can be configured and used as a different unit.

  

- default: root




Functions
---------




- login

 .. code-block:: python

    def login(data):
        host = data['host']
        username = data['username']
        password = data['password']
    
        fos.debug('on')
        if 'https' in data and not data['https']:
            fos.https('off')
        else:
            fos.https('on')
    
        fos.login(host, username, password)
    
    

- filter_router_ripng_data

 .. code-block:: python

    def filter_router_ripng_data(json):
        option_list = ['aggregate-address', 'default-information-originate', 'default-metric',
                       'distance', 'distribute-list', 'garbage-timer',
                       'interface', 'max-out-metric', 'neighbor',
                       'network', 'offset-list', 'passive-interface',
                       'redistribute', 'timeout-timer', 'update-timer']
        dictionary = {}
    
        for attribute in option_list:
            if attribute in json and json[attribute] is not None:
                dictionary[attribute] = json[attribute]
    
        return dictionary
    
    

- router_ripng

 .. code-block:: python

    def router_ripng(data, fos):
        vdom = data['vdom']
        router_ripng_data = data['router_ripng']
        filtered_data = filter_router_ripng_data(router_ripng_data)
        return fos.set('router',
                       'ripng',
                       data=filtered_data,
                       vdom=vdom)
    
    

- fortios_router

 .. code-block:: python

    def fortios_router(data, fos):
        login(data)
    
        methodlist = ['router_ripng']
        for method in methodlist:
            if data[method]:
                resp = eval(method)(data, fos)
                break
    
        fos.logout()
        return not resp['status'] == "success", resp['status'] == "success", resp
    
    

- main

 .. code-block:: python

    def main():
        fields = {
            "host": {"required": True, "type": "str"},
            "username": {"required": True, "type": "str"},
            "password": {"required": False, "type": "str", "no_log": True},
            "vdom": {"required": False, "type": "str", "default": "root"},
            "https": {"required": False, "type": "bool", "default": "False"},
            "router_ripng": {
                "required": False, "type": "dict",
                "options": {
                    "aggregate-address": {"required": False, "type": "list",
                                          "options": {
                                              "id": {"required": True, "type": "int"},
                                              "prefix6": {"required": False, "type": "str"}
                                          }},
                    "default-information-originate": {"required": False, "type": "str",
                                                      "choices": ["enable", "disable"]},
                    "default-metric": {"required": False, "type": "int"},
                    "distance": {"required": False, "type": "list",
                                 "options": {
                                     "access-list6": {"required": False, "type": "str"},
                                     "distance": {"required": False, "type": "int"},
                                     "id": {"required": True, "type": "int"},
                                     "prefix6": {"required": False, "type": "str"}
                                 }},
                    "distribute-list": {"required": False, "type": "list",
                                        "options": {
                                            "direction": {"required": False, "type": "str",
                                                          "choices": ["in", "out"]},
                                            "id": {"required": True, "type": "int"},
                                            "interface": {"required": False, "type": "str"},
                                            "listname": {"required": False, "type": "str"},
                                            "status": {"required": False, "type": "str",
                                                       "choices": ["enable", "disable"]}
                                        }},
                    "garbage-timer": {"required": False, "type": "int"},
                    "interface": {"required": False, "type": "list",
                                  "options": {
                                      "flags": {"required": False, "type": "int"},
                                      "name": {"required": True, "type": "str"},
                                      "split-horizon": {"required": False, "type": "str",
                                                        "choices": ["poisoned", "regular"]},
                                      "split-horizon-status": {"required": False, "type": "str",
                                                               "choices": ["enable", "disable"]}
                                  }},
                    "max-out-metric": {"required": False, "type": "int"},
                    "neighbor": {"required": False, "type": "list",
                                 "options": {
                                     "id": {"required": True, "type": "int"},
                                     "interface": {"required": False, "type": "str"},
                                     "ip6": {"required": False, "type": "str"}
                                 }},
                    "network": {"required": False, "type": "list",
                                "options": {
                                    "id": {"required": True, "type": "int"},
                                    "prefix": {"required": False, "type": "str"}
                                }},
                    "offset-list": {"required": False, "type": "list",
                                    "options": {
                                        "access-list6": {"required": False, "type": "str"},
                                        "direction": {"required": False, "type": "str",
                                                      "choices": ["in", "out"]},
                                        "id": {"required": True, "type": "int"},
                                        "interface": {"required": False, "type": "str"},
                                        "offset": {"required": False, "type": "int"},
                                        "status": {"required": False, "type": "str",
                                                   "choices": ["enable", "disable"]}
                                    }},
                    "passive-interface": {"required": False, "type": "list",
                                          "options": {
                                              "name": {"required": True, "type": "str"}
                                          }},
                    "redistribute": {"required": False, "type": "list",
                                     "options": {
                                         "metric": {"required": False, "type": "int"},
                                         "name": {"required": True, "type": "str"},
                                         "routemap": {"required": False, "type": "str"},
                                         "status": {"required": False, "type": "str",
                                                    "choices": ["enable", "disable"]}
                                     }},
                    "timeout-timer": {"required": False, "type": "int"},
                    "update-timer": {"required": False, "type": "int"}
    
                }
            }
        }
    
        module = AnsibleModule(argument_spec=fields,
                               supports_check_mode=False)
        try:
            from fortiosapi import FortiOSAPI
        except ImportError:
            module.fail_json(msg="fortiosapi module is required")
    
        global fos
        fos = FortiOSAPI()
    
        is_error, has_changed, result = fortios_router(module.params, fos)
    
        if not is_error:
            module.exit_json(changed=has_changed, meta=result)
        else:
            module.fail_json(msg="Error in repo", meta=result)
    
    



Module Source Code
------------------

.. code-block:: python

    #!/usr/bin/python
    from __future__ import (absolute_import, division, print_function)
    # Copyright 2018 Fortinet, Inc.
    #
    # This program is free software: you can redistribute it and/or modify
    # it under the terms of the GNU General Public License as published by
    # the Free Software Foundation, either version 3 of the License, or
    # (at your option) any later version.
    #
    # This program is distributed in the hope that it will be useful,
    # but WITHOUT ANY WARRANTY; without even the implied warranty of
    # MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    # GNU General Public License for more details.
    #
    # You should have received a copy of the GNU General Public License
    # along with this program.  If not, see <https://www.gnu.org/licenses/>.
    #
    # the lib use python logging can get it if the following is set in your
    # Ansible config.
    
    __metaclass__ = type
    
    ANSIBLE_METADATA = {'status': ['preview'],
                        'supported_by': 'community',
                        'metadata_version': '1.1'}
    
    DOCUMENTATION = '''
    ---
    module: fortios_router_ripng
    short_description: Configure RIPng.
    description:
        - This module is able to configure a FortiGate or FortiOS by
          allowing the user to configure router feature and ripng category.
          Examples includes all options and need to be adjusted to datasources before usage.
          Tested with FOS v6.0.2
    version_added: "2.8"
    author:
        - Miguel Angel Munoz (@mamunozgonzalez)
        - Nicolas Thomas (@thomnico)
    notes:
        - Requires fortiosapi library developed by Fortinet
        - Run as a local_action in your playbook
    requirements:
        - fortiosapi>=0.9.8
    options:
        host:
           description:
                - FortiOS or FortiGate ip adress.
           required: true
        username:
            description:
                - FortiOS or FortiGate username.
            required: true
        password:
            description:
                - FortiOS or FortiGate password.
            default: ""
        vdom:
            description:
                - Virtual domain, among those defined previously. A vdom is a
                  virtual instance of the FortiGate that can be configured and
                  used as a different unit.
            default: root
        https:
            description:
                - Indicates if the requests towards FortiGate must use HTTPS
                  protocol
            type: bool
            default: false
        router_ripng:
            description:
                - Configure RIPng.
            default: null
            suboptions:
                aggregate-address:
                    description:
                        - Aggregate address.
                    suboptions:
                        id:
                            description:
                                - Aggregate address entry ID.
                            required: true
                        prefix6:
                            description:
                                - Aggregate address prefix.
                default-information-originate:
                    description:
                        - Enable/disable generation of default route.
                    choices:
                        - enable
                        - disable
                default-metric:
                    description:
                        - Default metric.
                distance:
                    description:
                        - distance
                    suboptions:
                        access-list6:
                            description:
                                - Access list for route destination. Source router.access-list6.name.
                        distance:
                            description:
                                - Distance (1 - 255).
                        id:
                            description:
                                - Distance ID.
                            required: true
                        prefix6:
                            description:
                                - Distance prefix6.
                distribute-list:
                    description:
                        - Distribute list.
                    suboptions:
                        direction:
                            description:
                                - Distribute list direction.
                            choices:
                                - in
                                - out
                        id:
                            description:
                                - Distribute list ID.
                            required: true
                        interface:
                            description:
                                - Distribute list interface name. Source system.interface.name.
                        listname:
                            description:
                                - Distribute access/prefix list name. Source router.access-list6.name router.prefix-list6.name.
                        status:
                            description:
                                - status
                            choices:
                                - enable
                                - disable
                garbage-timer:
                    description:
                        - Garbage timer.
                interface:
                    description:
                        - RIPng interface configuration.
                    suboptions:
                        flags:
                            description:
                                - Flags.
                        name:
                            description:
                                - Interface name. Source system.interface.name.
                            required: true
                        split-horizon:
                            description:
                                - Enable/disable split horizon.
                            choices:
                                - poisoned
                                - regular
                        split-horizon-status:
                            description:
                                - Enable/disable split horizon.
                            choices:
                                - enable
                                - disable
                max-out-metric:
                    description:
                        - Maximum metric allowed to output(0 means 'not set').
                neighbor:
                    description:
                        - neighbor
                    suboptions:
                        id:
                            description:
                                - Neighbor entry ID.
                            required: true
                        interface:
                            description:
                                - Interface name. Source system.interface.name.
                        ip6:
                            description:
                                - IPv6 link-local address.
                network:
                    description:
                        - Network.
                    suboptions:
                        id:
                            description:
                                - Network entry ID.
                            required: true
                        prefix:
                            description:
                                - Network IPv6 link-local prefix.
                offset-list:
                    description:
                        - Offset list.
                    suboptions:
                        access-list6:
                            description:
                                - IPv6 access list name. Source router.access-list6.name.
                        direction:
                            description:
                                - Offset list direction.
                            choices:
                                - in
                                - out
                        id:
                            description:
                                - Offset-list ID.
                            required: true
                        interface:
                            description:
                                - Interface name. Source system.interface.name.
                        offset:
                            description:
                                - offset
                        status:
                            description:
                                - status
                            choices:
                                - enable
                                - disable
                passive-interface:
                    description:
                        - Passive interface configuration.
                    suboptions:
                        name:
                            description:
                                - Passive interface name. Source system.interface.name.
                            required: true
                redistribute:
                    description:
                        - Redistribute configuration.
                    suboptions:
                        metric:
                            description:
                                - Redistribute metric setting.
                        name:
                            description:
                                - Redistribute name.
                            required: true
                        routemap:
                            description:
                                - Route map name. Source router.route-map.name.
                        status:
                            description:
                                - status
                            choices:
                                - enable
                                - disable
                timeout-timer:
                    description:
                        - Timeout timer.
                update-timer:
                    description:
                        - Update timer.
    '''
    
    EXAMPLES = '''
    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure RIPng.
        fortios_router_ripng:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          router_ripng:
            aggregate-address:
             -
                id:  "4"
                prefix6: "<your_own_value>"
            default-information-originate: "enable"
            default-metric: "7"
            distance:
             -
                access-list6: "<your_own_value> (source router.access-list6.name)"
                distance: "10"
                id:  "11"
                prefix6: "<your_own_value>"
            distribute-list:
             -
                direction: "in"
                id:  "15"
                interface: "<your_own_value> (source system.interface.name)"
                listname: "<your_own_value> (source router.access-list6.name router.prefix-list6.name)"
                status: "enable"
            garbage-timer: "19"
            interface:
             -
                flags: "21"
                name: "default_name_22 (source system.interface.name)"
                split-horizon: "poisoned"
                split-horizon-status: "enable"
            max-out-metric: "25"
            neighbor:
             -
                id:  "27"
                interface: "<your_own_value> (source system.interface.name)"
                ip6: "<your_own_value>"
            network:
             -
                id:  "31"
                prefix: "<your_own_value>"
            offset-list:
             -
                access-list6: "<your_own_value> (source router.access-list6.name)"
                direction: "in"
                id:  "36"
                interface: "<your_own_value> (source system.interface.name)"
                offset: "38"
                status: "enable"
            passive-interface:
             -
                name: "default_name_41 (source system.interface.name)"
            redistribute:
             -
                metric: "43"
                name: "default_name_44"
                routemap: "<your_own_value> (source router.route-map.name)"
                status: "enable"
            timeout-timer: "47"
            update-timer: "48"
    '''
    
    RETURN = '''
    build:
      description: Build number of the fortigate image
      returned: always
      type: string
      sample: '1547'
    http_method:
      description: Last method used to provision the content into FortiGate
      returned: always
      type: string
      sample: 'PUT'
    http_status:
      description: Last result given by FortiGate on last operation applied
      returned: always
      type: string
      sample: "200"
    mkey:
      description: Master key (id) used in the last call to FortiGate
      returned: success
      type: string
      sample: "key1"
    name:
      description: Name of the table used to fulfill the request
      returned: always
      type: string
      sample: "urlfilter"
    path:
      description: Path of the table used to fulfill the request
      returned: always
      type: string
      sample: "webfilter"
    revision:
      description: Internal revision number
      returned: always
      type: string
      sample: "17.0.2.10658"
    serial:
      description: Serial number of the unit
      returned: always
      type: string
      sample: "FGVMEVYYQT3AB5352"
    status:
      description: Indication of the operation's result
      returned: always
      type: string
      sample: "success"
    vdom:
      description: Virtual domain used
      returned: always
      type: string
      sample: "root"
    version:
      description: Version of the FortiGate
      returned: always
      type: string
      sample: "v5.6.3"
    
    '''
    
    from ansible.module_utils.basic import AnsibleModule
    
    fos = None
    
    
    def login(data):
        host = data['host']
        username = data['username']
        password = data['password']
    
        fos.debug('on')
        if 'https' in data and not data['https']:
            fos.https('off')
        else:
            fos.https('on')
    
        fos.login(host, username, password)
    
    
    def filter_router_ripng_data(json):
        option_list = ['aggregate-address', 'default-information-originate', 'default-metric',
                       'distance', 'distribute-list', 'garbage-timer',
                       'interface', 'max-out-metric', 'neighbor',
                       'network', 'offset-list', 'passive-interface',
                       'redistribute', 'timeout-timer', 'update-timer']
        dictionary = {}
    
        for attribute in option_list:
            if attribute in json and json[attribute] is not None:
                dictionary[attribute] = json[attribute]
    
        return dictionary
    
    
    def router_ripng(data, fos):
        vdom = data['vdom']
        router_ripng_data = data['router_ripng']
        filtered_data = filter_router_ripng_data(router_ripng_data)
        return fos.set('router',
                       'ripng',
                       data=filtered_data,
                       vdom=vdom)
    
    
    def fortios_router(data, fos):
        login(data)
    
        methodlist = ['router_ripng']
        for method in methodlist:
            if data[method]:
                resp = eval(method)(data, fos)
                break
    
        fos.logout()
        return not resp['status'] == "success", resp['status'] == "success", resp
    
    
    def main():
        fields = {
            "host": {"required": True, "type": "str"},
            "username": {"required": True, "type": "str"},
            "password": {"required": False, "type": "str", "no_log": True},
            "vdom": {"required": False, "type": "str", "default": "root"},
            "https": {"required": False, "type": "bool", "default": "False"},
            "router_ripng": {
                "required": False, "type": "dict",
                "options": {
                    "aggregate-address": {"required": False, "type": "list",
                                          "options": {
                                              "id": {"required": True, "type": "int"},
                                              "prefix6": {"required": False, "type": "str"}
                                          }},
                    "default-information-originate": {"required": False, "type": "str",
                                                      "choices": ["enable", "disable"]},
                    "default-metric": {"required": False, "type": "int"},
                    "distance": {"required": False, "type": "list",
                                 "options": {
                                     "access-list6": {"required": False, "type": "str"},
                                     "distance": {"required": False, "type": "int"},
                                     "id": {"required": True, "type": "int"},
                                     "prefix6": {"required": False, "type": "str"}
                                 }},
                    "distribute-list": {"required": False, "type": "list",
                                        "options": {
                                            "direction": {"required": False, "type": "str",
                                                          "choices": ["in", "out"]},
                                            "id": {"required": True, "type": "int"},
                                            "interface": {"required": False, "type": "str"},
                                            "listname": {"required": False, "type": "str"},
                                            "status": {"required": False, "type": "str",
                                                       "choices": ["enable", "disable"]}
                                        }},
                    "garbage-timer": {"required": False, "type": "int"},
                    "interface": {"required": False, "type": "list",
                                  "options": {
                                      "flags": {"required": False, "type": "int"},
                                      "name": {"required": True, "type": "str"},
                                      "split-horizon": {"required": False, "type": "str",
                                                        "choices": ["poisoned", "regular"]},
                                      "split-horizon-status": {"required": False, "type": "str",
                                                               "choices": ["enable", "disable"]}
                                  }},
                    "max-out-metric": {"required": False, "type": "int"},
                    "neighbor": {"required": False, "type": "list",
                                 "options": {
                                     "id": {"required": True, "type": "int"},
                                     "interface": {"required": False, "type": "str"},
                                     "ip6": {"required": False, "type": "str"}
                                 }},
                    "network": {"required": False, "type": "list",
                                "options": {
                                    "id": {"required": True, "type": "int"},
                                    "prefix": {"required": False, "type": "str"}
                                }},
                    "offset-list": {"required": False, "type": "list",
                                    "options": {
                                        "access-list6": {"required": False, "type": "str"},
                                        "direction": {"required": False, "type": "str",
                                                      "choices": ["in", "out"]},
                                        "id": {"required": True, "type": "int"},
                                        "interface": {"required": False, "type": "str"},
                                        "offset": {"required": False, "type": "int"},
                                        "status": {"required": False, "type": "str",
                                                   "choices": ["enable", "disable"]}
                                    }},
                    "passive-interface": {"required": False, "type": "list",
                                          "options": {
                                              "name": {"required": True, "type": "str"}
                                          }},
                    "redistribute": {"required": False, "type": "list",
                                     "options": {
                                         "metric": {"required": False, "type": "int"},
                                         "name": {"required": True, "type": "str"},
                                         "routemap": {"required": False, "type": "str"},
                                         "status": {"required": False, "type": "str",
                                                    "choices": ["enable", "disable"]}
                                     }},
                    "timeout-timer": {"required": False, "type": "int"},
                    "update-timer": {"required": False, "type": "int"}
    
                }
            }
        }
    
        module = AnsibleModule(argument_spec=fields,
                               supports_check_mode=False)
        try:
            from fortiosapi import FortiOSAPI
        except ImportError:
            module.fail_json(msg="fortiosapi module is required")
    
        global fos
        fos = FortiOSAPI()
    
        is_error, has_changed, result = fortios_router(module.params, fos)
    
        if not is_error:
            module.exit_json(changed=has_changed, meta=result)
        else:
            module.fail_json(msg="Error in repo", meta=result)
    
    
    if __name__ == '__main__':
        main()


