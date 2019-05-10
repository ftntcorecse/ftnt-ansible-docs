================
fsm_report_query
================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: SUBMIT REPORT
      fsm_report_query:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        report_file_path: "/root/top_fortisiem_events_by_count.xml"
        export_json_to_file_path: "/root/report.json"
        export_xml_to_file_path: "/root/report.xml"
        export_csv_to_file_path: "/root/report.csv"
        
    - name: GET REPORT WITH RELATIVE TIME DEFINED
      fsm_report_query:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        report_file_path: "/root/top_fortisiem_events_by_count.xml"
        report_relative_mins: "60"
    
    - name: GET REPORT WITH ABSOLUTE TIME DEFINED
      fsm_report_query:
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        ignore_ssl_errors: "enable"
        report_file_path: "/root/top_fortisiem_events_by_count.xml"
        report_absolute_begin_date: "04/17/2019"
        report_absolute_begin_time: "060000"
        report_absolute_end_date: "04/17/2019"
        report_absolute_end_time: "070000"



Playbook File Examples
----------------------


fsm_submit_large_report.yml
+++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET RESULTS FROM REPORT
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: SUBMIT LARGE REPORT
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "/root/all_fw_events.xml"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/large_report.json"
            export_xml_to_file_path: "/root/Large_report.xml"
            export_csv_to_file_path: "/root/large_report.csv"
    
    


top_fortisiem_events_by_count.xml
+++++++++++++++++++++++++++++++++

.. code-block:: xml

           <?xml version="1.0" encoding="UTF-8"?>
    <Reports>
        <Report baseline="" rsSync="">
            <Name>Top FortiSIEM Events By Count</Name>
            <Description>Ranks the events by the number of times they have occurred in a given time period.</Description>
            <CustomerScope groupByEachCustomer="false">
            </CustomerScope>
            <SelectClause>
                <AttrList>eventType,COUNT(*)</AttrList>
            </SelectClause>
            <OrderByClause>
                <AttrList>COUNT(*) DESC</AttrList>
            </OrderByClause>
            <PatternClause window="3600">
                <SubPattern id="1164394" name="Filter_OVERALL_STATUS">
                    <GroupByAttr>eventType</GroupByAttr>
                </SubPattern>
            </PatternClause>
            <userRoles>
                <roles custId="0">1169250</roles>
            </userRoles>
            <SyncOrgs/>
        </Report>
    </Reports>

fsm_incident_report.yml
+++++++++++++++++++++++

.. code-block:: yaml



    - name: GET RESULTS FROM REPORT
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET AN INCIDENT REPORT DIFFERENT MORE DETAIL
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "top-devices-and-incidents.xml"
            report_absolute_begin_date: "04/13/2019"
            report_absolute_begin_time: "060000"
            report_absolute_end_date: "04/18/2019"
            report_absolute_end_time: "150000"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/incident_report.json"
            export_xml_to_file_path: "/root/incident_report.xml"
    
    


fsm_submit_timed_report.yml
+++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET RESULTS FROM REPORT
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: GET REPORT WITH RELATIVE TIME DEFINED
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "/root/top_fortisiem_events_by_count.xml"
            report_relative_mins: "60"
    
        - name: GET REPORT WITH ABSOLUTE TIME DEFINED
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "/root/top_fortisiem_events_by_count.xml"
            report_absolute_begin_date: "04/17/2019"
            report_absolute_begin_time: "060000"
            report_absolute_end_date: "04/17/2019"
            report_absolute_end_time: "070000"
    


fsm_msp_submit_large_report.yml
+++++++++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET RESULTS FROM REPORT
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
        - name: MSP SUBMIT LARGE REPORT
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "/root/all_fw_events.xml"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/msp_large_report.json"
            export_xml_to_file_path: "/root/msp_large_report.xml"
            export_csv_to_file_path: "/root/msp_large_report.csv"
    
    


fsm_msp_submit_report.yml
+++++++++++++++++++++++++

.. code-block:: yaml



    - name: GET RESULTS FROM REPORT
      hosts: FortiSIEM_MSP
      connection: local
      gather_facts: False
    
      tasks:
        - name: MSP SUBMIT REPORT
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "testOrg/api_user"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "/root/msp-report.xml"
            export_json_to_screen: "enable"
            export_json_to_file_path: "/root/msp_report.json"
            export_xml_to_file_path: "/root/msp__report.xml"
    
    


all_fw_events.xml
+++++++++++++++++

.. code-block:: xml

           <?xml version="1.0" encoding="UTF-8"?><Reports><Report baseline="" rsSync=""><Name>Get_All_firewall_events_last_15m</Name><Description>Get_All_firewall_events_last_15m - 03:13:07 PM Apr 09 2019</Description><CustomerScope groupByEachCustomer="true">
    <Include>1</Include>
    <Exclude/>
    </CustomerScope><SelectClause>
    <AttrList>phRecvTime,reptDevIpAddr,eventType,eventName,rawEventMsg</AttrList>
    </SelectClause><PatternClause>
    <SubPattern id="2414751" name="">
    <SingleEvtConstr>(reptDevIpAddr = 10.0.0.254) AND (phCustId IN (1))</SingleEvtConstr>
    </SubPattern>
    </PatternClause><userRoles>
    <roles custId="1">1698800</roles>
    </userRoles><SyncOrgs/><ReportInterval>
    <Low>1554839835</Low>
    <High>1554840734</High>
    </ReportInterval></Report></Reports>
    


fsm_submit_report.yml
+++++++++++++++++++++

.. code-block:: yaml



    - name: GET RESULTS FROM REPORT
      hosts: FortiSIEM
      connection: local
      gather_facts: False
    
      tasks:
        - name: SUBMIT REPORT
          fsm_report_query:
            host: "{{ inventory_hostname }}"
            username: "{{ username }}"
            password: "{{ password }}"
            ignore_ssl_errors: "enable"
            report_file_path: "/root/top_fortisiem_events_by_count.xml"
            export_json_to_file_path: "/root/report.json"
            export_xml_to_file_path: "/root/report.xml"
            export_csv_to_file_path: "/root/report.csv"
    
    




