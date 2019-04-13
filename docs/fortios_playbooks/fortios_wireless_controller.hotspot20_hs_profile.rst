================================================
fortios_wireless_controller.hotspot20_hs_profile
================================================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure hotspot profile.
        fortios_wireless_controller.hotspot20_hs_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_hs_profile:
            state: "present"
            3gpp-plmn: "<your_own_value> (source wireless-controller.hotspot20.anqp-3gpp-cellular.name)"
            access-network-asra: "enable"
            access-network-esr: "enable"
            access-network-internet: "enable"
            access-network-type: "private-network"
            access-network-uesa: "enable"
            anqp-domain-id: "9"
            bss-transition: "enable"
            conn-cap: "<your_own_value> (source wireless-controller.hotspot20.h2qp-conn-capability.name)"
            deauth-request-timeout: "12"
            dgaf: "enable"
            domain-name: "<your_own_value>"
            gas-comeback-delay: "15"
            gas-fragmentation-limit: "16"
            hessid: "<your_own_value>"
            ip-addr-type: "<your_own_value> (source wireless-controller.hotspot20.anqp-ip-address-type.name)"
            l2tif: "enable"
            nai-realm: "<your_own_value> (source wireless-controller.hotspot20.anqp-nai-realm.name)"
            name: "default_name_21"
            network-auth: "<your_own_value> (source wireless-controller.hotspot20.anqp-network-auth-type.name)"
            oper-friendly-name: "<your_own_value> (source wireless-controller.hotspot20.h2qp-operator-name.name)"
            osu-provider:
             -
                name: "default_name_25 (source wireless-controller.hotspot20.h2qp-osu-provider.name)"
            osu-ssid: "<your_own_value>"
            pame-bi: "disable"
            proxy-arp: "enable"
            qos-map: "<your_own_value> (source wireless-controller.hotspot20.qos-map.name)"
            roaming-consortium: "<your_own_value> (source wireless-controller.hotspot20.anqp-roaming-consortium.name)"
            venue-group: "unspecified"
            venue-name: "<your_own_value> (source wireless-controller.hotspot20.anqp-venue-name.name)"
            venue-type: "unspecified"
            wan-metrics: "<your_own_value> (source wireless-controller.hotspot20.h2qp-wan-metric.name)"
            wnm-sleep-mode: "enable"



Playbook File Examples
----------------------

<<<<<<< Updated upstream

../ansible_fgt_modules/v6.0.2/wireless_controller.hotspot20/fortios_wireless_controller.hotspot20_hs_profile_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure hotspot profile.
        fortios_wireless_controller.hotspot20_hs_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_hs_profile:
            state: "present"
            3gpp-plmn: "<your_own_value> (source wireless-controller.hotspot20.anqp-3gpp-cellular.name)"
            access-network-asra: "enable"
            access-network-esr: "enable"
            access-network-internet: "enable"
            access-network-type: "private-network"
            access-network-uesa: "enable"
            anqp-domain-id: "9"
            bss-transition: "enable"
            conn-cap: "<your_own_value> (source wireless-controller.hotspot20.h2qp-conn-capability.name)"
            deauth-request-timeout: "12"
            dgaf: "enable"
            domain-name: "<your_own_value>"
            gas-comeback-delay: "15"
            gas-fragmentation-limit: "16"
            hessid: "<your_own_value>"
            ip-addr-type: "<your_own_value> (source wireless-controller.hotspot20.anqp-ip-address-type.name)"
            l2tif: "enable"
            nai-realm: "<your_own_value> (source wireless-controller.hotspot20.anqp-nai-realm.name)"
            name: "default_name_21"
            network-auth: "<your_own_value> (source wireless-controller.hotspot20.anqp-network-auth-type.name)"
            oper-friendly-name: "<your_own_value> (source wireless-controller.hotspot20.h2qp-operator-name.name)"
            osu-provider:
             -
                name: "default_name_25 (source wireless-controller.hotspot20.h2qp-osu-provider.name)"
            osu-ssid: "<your_own_value>"
            pame-bi: "disable"
            proxy-arp: "enable"
            qos-map: "<your_own_value> (source wireless-controller.hotspot20.qos-map.name)"
            roaming-consortium: "<your_own_value> (source wireless-controller.hotspot20.anqp-roaming-consortium.name)"
            venue-group: "unspecified"
            venue-name: "<your_own_value> (source wireless-controller.hotspot20.anqp-venue-name.name)"
            venue-type: "unspecified"
            wan-metrics: "<your_own_value> (source wireless-controller.hotspot20.h2qp-wan-metric.name)"
            wnm-sleep-mode: "enable"



=======
%%PB_FILE_EXAMPLE_TOKEN%%
>>>>>>> Stashed changes

