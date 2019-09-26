# Advanced Template Net Mikrotik SNMPv2

Template based on original Template Net Mikrotik SNMPv2 from stock Zabbix 4.0

## Improvements (after forking)
* Added limit to Network Interfaces Discovery - discover only interfaces with Comment filled
* IP Addresses Discovery disabled by default
* Added Neighbor Discovery rules
* Added PoE Discovery rules
* Added License information items
* Added DHCP lease count
* Added variuos Health/Environment/Inventory discovery rules and items

## Installation

Tested on Zabbix 4.0, RB4011iGS+RM, RBD52G-5HacD2HnD-TC, RB941-2nD.

* At first you need to import `Advanced_Template_Module_Interfaces_SNMPv2.xml`. This module is linked with the main template.
* Then import  the main module `Advanced_Template_Net_Mikrotik_SNMPv2.xml`

For correct IP discovery working, you need to add Regular Expressions (see screenshot), for discovering only public IPs:
```
IP addresses for discovery	
1	»	^(172\.(1+[6-9]|2+[0-9]|3+[0-2])\.)+[0-9]{1,3}+\.+[0-9]{1,3}$	[Result is FALSE]
2	»	^(10\.[0-9]{1,3}\.)+[0-9]{1,3}+\.+[0-9]{1,3}$			[Result is FALSE]
3	»	^(192\.168\.)+[0-9]{1,3}+\.+[0-9]{1,3}$				[Result is FALSE]
```
![RegExp IP addresses for discovery](/regexp/regexp-ip_addresses_for_discovery.png?raw=true "RegExp IP addresses for discovery")
