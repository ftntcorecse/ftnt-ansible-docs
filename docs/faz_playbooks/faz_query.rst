=========
faz_query
=========


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: GET STATUS OF TASK ID
      faz_query:
        adom: "ansible"
        object: "task"
        task_id: "3"
    
    - name: USE CUSTOM TYPE TO QUERY AVAILABLE SCRIPTS
      faz_query:
        adom: "ansible"
        object: "custom"
        custom_endpoint: "/dvmdb/adom/ansible/script"
        custom_dict: { "type": "cli" }



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

