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
Until we get this code past the Pull-Request process with Redhat, it should be released in Ansible 2.9+. Until then...

Step 2a - Base Ansible Install
"""""""""""""""""""""""""""""""

- First, make sure Ansible is already installed, and shows version 2.7+.
- If version isn't 2.7+, upgrade.

Step 2b - Clone FNDN Git Repo
""""""""""""""""""""""""""""""

- Second, use GIT to clone the FNDN repo: https://github.com/ftntcorecse/fndn_ansible

Step 2c - Install Module Utils
"""""""""""""""""""""""""""""""
- The module_utils need to be copied to their correct locations.

- Find the module utils under fndn_ansible/fortisiem/module_utils/network/fortisiem/, copy them all to: .

.. code-block:: shell

    /usr/lib/python2.7/dist-packages/ansible/module_utils/network/fortisiem/

- If you're unsure where to find this path on your own system, run this command:

.. code-block:: shell

    find /usr -name "ansible"

- ... and the path under a python dist-packages should present itself. It will be similar to the path above. Create the directory if required.

Step 2d - Install Modules
""""""""""""""""""""""""""
- The modules can be copied to any directory such as /usr/ansible_modules,
  as long as the library = <folder_path> line in /etc/ansible/ansible.cfg is edited to include that path.

- Edit /usr/ansible/ansible.cfg to ensure the library = <module_folder_path> is true.
  No recursion, ensure all modules flat in that folder.

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


Using Ansible Vault to Hide Logins
==================================
There are many ways to implement Ansible Vault. Feel free to use any method desired.
If no previous experience with Ansible Vault exists, we recommend starting with this method:

- https://medium.com/@schogini/ansible-vault-variables-a-tiny-demonstration-to-handle-secrets-a36132971015

The procedure is simple:

- Use 'ansible-vault encrypt string' on ansible host to create a vault string.
- Replace vault string in HOSTS or Variables file, for the username/password or both.

.. code-block:: yaml

  fortisiem:
    ansible_user: "ansible"
    ansible_host: "10.7.220.35"
    ansible_password: !vault |
      $ANSIBLE_VAULT;1.1;AES256
      61366437333436393062623438393663366138633265363930313763383964313130643134383839
      3630663661626365366334646661303338313866373032330a636165373833366166616465373830
      34356466653464313134313664613435356238666139623165623132306538336565376265356633
      6362396137306466630a666562393637353863626436376132643464366661323734363830383164
      6366

- Add a reference to the variable file/vault file from the playbook itself:

.. code-block:: yaml

    ---
    - name: Query FSM
      hosts: FortiSIEM
      connection: local
      gather_facts: False
      vars_files:
        - group_vars/vault.yml

- And then run playbooks with --ask-vault-pass, or setup a password file to provide it.

It is recommended to keep vault secret variables in their own files, so the un-encrypted variables could be read by peers.

Additional Ansible Vault tutorials, references, and alternative implementation methods:

- https://docs.ansible.com/ansible/latest/user_guide/playbooks_vault.html

- https://www.expressvpn.com/blog/ansible-variables-vaults/

- https://www.digitalocean.com/community/tutorials/how-to-use-vault-to-protect-sensitive-ansible-data-on-ubuntu-16-04


