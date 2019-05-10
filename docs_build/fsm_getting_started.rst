###############
Getting Started
###############
This guide will assist in the initial configuration of Ansible
to work with FortiSIEM modules.



Introduction
============

The FortiSIEM Modules are connection: local modules. In other words, they do not use a plugin.

The FortiSIEM API is stateless, so a username and password authentication header must be sent with every request.
Thus, a connection plug-in (which expects an API token or Session ID) will never likely be developed for FortiSIEM modules.

As of this writing, Ansible Vault is a valid option for encoding and storing the username/password.


Pre-Requisites
==============

- Minimum Ansible Version: 2.7+
- Minimum Python Version: 2.7+

  - Works with Python 3.x

- Minimum FortiSIEM Version: 5.0+


Installation
=============================

Step 1 - Auto Installation Method (Currently Unavailable)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Until we PR these modules and module_utils, this method is unavailable. Please see the manual installation below.

Expect this installation method to be un-available when Ansible 2.9+ is released, or perhaps a maintenance release to 2.8+.


Step 2 (Optional) - Manual Installation Method
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Summary
"""""""

- These most-recent versions are located on the official FNDN github repo here:
  https://github.com/ftntcorecse/fndn_ansible

Steps
"""""

- First, make sure Ansible is already installed, and shows version 2.7+.

- Second, use GIT to clone the repo above: https://github.com/ftntcorecse/fndn_ansible

- The module_utils need to be copied to their correct locations. On Ubuntu running Python 2.7, the path is:

.. code-block:: shell

   /usr/lib/python2.7/dist-packages/ansible/module_utils/network/fortisiem/

- If you're unsure where to find this path on your own system, run this command:

.. code-block:: shell

    find /usr -name "ansible"

- ... and the path under a python dist-packages should present itself. It will be similar to the path above.

- The modules can be copied to any directory such as /usr/ansible_modules,
  as long as the library = <folder_path> line in /etc/ansible/ansible.cfg is edited to include that path.

- For other custom module path methods, see this guide:
  https://docs.ansible.com/ansible/latest/dev_guide/developing_locally.html#adding-a-module-locally


Step 3 - Inventory File
^^^^^^^^^^^^^^^^^^^^^^^^^
The FortiSIEM Super should be added to the hosts file under the header [FortiSIEM]. It should also
have declarations for username and password. The username must be in org/user format, and the password must be valid,
and the account must have admin privileges of some kind in FortiSIEM. We recommend creating a user named "ansible"
with the permissions required, and using that account in the hosts fie.

.. code-block:: shell

    [FortiSIEM]
    10.0.0.15

    [FortiSIEM_MSP]
    10.7.220.61

    [fsm_api:children]
    FortiSIEM
    FortiSIEM_MSP

    [fsm_api:vars]
    username=super/api_user
    password=Fortinet!1



Step 4 - Playbook Test
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ansible should be ready to test now. Copy the following code block into a file named "test_fsm.yml":

.. code-block:: yaml

    ---
    - name: CUSTOM QUERIES
      hosts: FortiSIEM
      connection: local
      gather_facts: False

      tasks:
        - name: SIMPLE CUSTOM QUERY TO CMDB
          fsm_custom_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            mode: "get"
            export_json_to_screen: "enable"
            uri: "/phoenix/rest/config/Domain"

... and then run it with the following command:

.. code-block:: shell

  ansible-playbook test_fsm.yml -vvvv

If successful, it should report OK with Green Text and show various information
about the target FortiSIEM Organizations.

If not successful, double check the hosts file, username/password combo,
and that the credentials have appropriate RBAC access in FortiSIEM.
The -vvvv verbose mode should indicate where the issue lies.



