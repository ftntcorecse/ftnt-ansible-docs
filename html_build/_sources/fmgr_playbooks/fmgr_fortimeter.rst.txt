===============
fmgr_fortimeter
===============


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SET LICENSING MODE ON FORTIMETER DEVICE to ALL
      fmgr_fortimeter:
        object: "device"
        adom: "ansible"
        device_unique_name: "FOSVM1FGPRJ411DD"
        fortimeter_utm_level: "all"
    
    - name: SET LICENSING MODE ON FORTIMETER DEVICE to a COMBO
      fmgr_fortimeter:
        object: "device"
        adom: "ansible"
        device_unique_name: "FOSVM1FGPRJ411DD"
        fortimeter_utm_level: "fw, ips, av"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

