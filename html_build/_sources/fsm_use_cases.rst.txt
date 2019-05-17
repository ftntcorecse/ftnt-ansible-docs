###############
Use Cases
###############
In this guide will be a list of use cases for the Ansible modules provided for FortiSIEM.
These are just some examples of what is possible. You are limited only by your imagination, with the power
of ansible. If you develop a unique use case, we want to hear about it!



Introduction
============
The FortiSIEM Engineering Team has maintained an API guide for quite some time now.

The Core CSE DevOps Team have provided Ansible modules for all published API's in above referenced guide.

The results from their efforts are the following ten modules:

- fsm_cmdb_devices
- fsm_credentials
- fsm_custom_query
- fsm_device_monitors
- fsm_discovery
- fsm_maintenance
- fsm_organizations
- fsm_report_query
- fsm_send_syslog
- fsm_verify_device_ip

Module Use Cases
=================

fsm_cmdb_devices
^^^^^^^^^^^^^^^^^

- This module can be used to verify the presence of a device in FortiSIEM CMDB.
- It can called to get detailed information on a single device, or simple information on many devices.
- Able to return discovered methods, enabling the audit of credentials on devices.
- Can be used in Ansible to cross-reference inventory with third-party systems.
- Allows FortiSIEM inventory to be used in Ansible pipelines.


fsm_credentials
^^^^^^^^^^^^^^^^^^^^

- This module can be used to add or update credentials.
- Allows update/add of IP Mappings for credentials.
- Ad-hoc credential mappings, for commmon credentials, would assist in automatic discovery
- Pull list of Windows systems from another list accessible to ansible, create mappings for each
- Do the same ^ for any other type of system
- When new server detected, if IP isn't under an existing credential mapping, map it.


fsm_custom_query
^^^^^^^^^^^^^^^^^^^^

- This module allows the query of any URI endpoint on a FortiSIEM system:

  - XML payloads are supported
  - Allows use of any endpoint

- Limited by your imagination. All of FortiSIEM is ran on APIs. 90% of them aren't documented.
- Allows the integration of almost any FortiSIEM API endpoint, with any supported Ansible device.


fsm_device_monitors
^^^^^^^^^^^^^^^^^^^^

- Quickly discover which monitors are in place for a FortiSIEM system.

  - Use this information to audit devices, or cross-reference with a list from another system.

- Used to discover if monitors are in place for a device, or not.


fsm_discovery
^^^^^^^^^^^^^^^

- Allows the ad-hoc discovery of devices.
- If fsm_cmdb_devices or fsm_custom_query or fsm_report_query or
  fsm_verify_device doesn't provide enough proof that a device is discovered, it can be remediated here.
- Keep FortiSIEM devices in-sync with another system or list accessible to Ansible.


fsm_maintenance
^^^^^^^^^^^^^^^^^^^^

- Add or Delete FortiSIEM Maintenance Calendar Objects.
- Allows the synchronization of Maintenance Periods with other systems.


fsm_organizations
^^^^^^^^^^^^^^^^^^^^

- Allows the addition or updating of any Organization, for a FortiSIEM instance in MSP mode.
- Create a web-hook into another system via Ansible to automatically create new
  organizations in FortiSIEM as they are created in other systems.
- Allows the definition of Collectors
- Get a list of organizations on a MSP instance of FortiSIEM.


fsm_report_query
^^^^^^^^^^^^^^^^^^^^

- Allows the query of almost all data contained with FortiSIEM.
- How to Setup New Report:

  - Step 1 | Create the desired report in FSM GUI
  - Step 2 | Export to XML
  - Step 3 | Copy XML to Ansible Host
  - Step 4 | Run XML report in Ansible to provide any information contained within FortiSIEM.

- Do not under-estimate the power of this module. A report can be created for almost ANYTHING.

fsm_send_syslog
^^^^^^^^^^^^^^^^^^^^

- Allows the logging of virtually any source to FortiSIEM via Syslog.
- Network protocols include UDP, TCP, and TCP over TLS.
- Usually requires a parser to understand what is being sent.
- An "ansible-generic" parser could be created to take in all events that happen to Ansible.
- Used to send events to FortiSIEM that are discovered by Ansible, or to track Ansible data pipelines.

fsm_verify_device_ip
^^^^^^^^^^^^^^^^^^^^

- Checks by IP address only
- Returns if an IP address is present in the CMDB, if it has any events within the last 15m, and if
  any monitors are currently active.
- Scores devices based on the amount of data in the system for each device.
- Possible to send device scores to a text file for comparison.
- Makes identification of devices, "lacking in data", much more easy.
