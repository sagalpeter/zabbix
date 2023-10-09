# Zabbix template for Samsung MIM-B19N modbus interface

## Prerequisites
- Samsung AC installation with MIM-B19N interface module
- TCP modbus gateway (ex. [mbusd](https://github.com/3cky/mbusd)) or local serial interface
- Zabbix version 6.0 and above

## Installation
- [Import](https://www.zabbix.com/documentation/6.0/en/manual/xml_export_import/templates) template file `Samsung_MIM-B19N.yaml` to zabbix

## Configuration
Configuration of this template is carried by modification of template's macros
- `{$MODBUS_ADDRESS}`: numeric modbus address of MIM-B19N interface (set by using the DIP and rotary switches on module board)
- `{$MODBUS_REGISTERS}`: JSON-style list of first registers for every connected indoor unit, should be multiples of 50. For example two units: `[50,100]`
- `{$MODBUS_URL}`: [endpoint url](https://www.zabbix.com/integrations/modbus) to modbus gateway/serial interface. Example `tcp://localhost:511` or `rtu://COM1:9600:8n1`

## Items
This template contains 4 global items for outdoor unit and one discovery rule for every indoor units, as defined in `{$MODBUS_REGISTERS}` macro.

## Triggers
Triggers are only configured for error-code items, and for situation when defrosting of outdoor unit is in operation.

## Value mappings
Value mappings are added for some items in case documentation has explained values.
