# Zabbix template for APC PowerChute UPS monitoring by SNMP

## Prerequisites
- APC PowerChute with enabled SNMP accessible from zabbix
- Zabbix version 6.0 and above with SNMP enabled

## Installation
- [Import](https://www.zabbix.com/documentation/6.0/en/manual/xml_export_import/templates) template file `APC_Powerchute_UPS_SNMP.yaml` to zabbix
- copy `Powernet-MIB.txt` into `/usr/share/snmp/mibs` or equivalent directory

## Configuration
There is no configuration needed, as everything is carried out by discovery rule.

## Items
Items are automatically created for every discovered UPS.

## Triggers
There is only one trigger for UPS status not onLine.

## Value mappings
Value mappings are added for some items in case documentation (MIB) has explained values.
