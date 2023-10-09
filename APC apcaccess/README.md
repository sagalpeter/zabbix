# Zabbix template for APC apcaccess based monitoring

## Prerequisites
- apcupsd configured & running
- Zabbix version 6.0 and above

## Installation
- [Import](https://www.zabbix.com/documentation/6.0/en/manual/xml_export_import/templates) template file `APC_apcaccess.yaml` to zabbix
- copy `aps_apcaccess.conf` into `/etc/zabbix/zabbix_agentd.d/`

## Configuration
There is no configuration except macro `{$DISCARD.SECONDS}` for setting heartbeat for throttling.

## Items
There are static items only, one master item getting output of apcaccess command, and others dependent with regular expressions preprocessing.

## Triggers
There are two triggers, one for UPS not online, and second for battery replacement alarm.
