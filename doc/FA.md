# Fan
## Features
- Supports fan speed
- Supports preset mode
- Supports oscillation
- Supports tilting

## Customize

Set the shifts of the fan device except "Off".

```
{"speed_count": 3}
```

## Entities
### Default entity
EntityID | Class | Description
--- | --- | ---
fan.{DEVICEID}_fan | fan | Fan entity

### Extra entities

EntityID | Class | Description
--- | --- | ---
sensor.{DEVICEID}_oscillation_mode | select | Oscillation Mode
sensor.{DEVICEID}_oscillation_angle | select | Oscillation Angle
sensor.{DEVICEID}_tilting_angle | select | Tilting Angle
sensor.{DEVICEID}_child_lock | lock | Child Lock
sensor.{DEVICEID}_oscillate | switch | Oscillate
sensor.{DEVICEID}_power | switch | Power


## Services
following extra services will be made

### midea_ac_lan.set_attribute

[![Service](https://my.home-assistant.io/badges/developer_call_service.svg)](https://my.home-assistant.io/redirect/developer_call_service/?service=midea_ac_lan.set_attribute)

Set the attribute of fan. Service data:

Name | Description
--- | ---
device_id | The Appliance code (Device ID) of appliance
attribute | "child_lock"<br/>"oscillate"
value | true or false

Name | Description
--- | ---
device_id | The Appliance code (Device ID) of appliance
attribute | "oscillation_mode"
value | "Off"<br/>"Oscillation"<br/>"Tilting"<br/>"Curve-W"<br/>"Curve-8"<br/>"Reserved"<br/>"Both"

Name | Description
--- | ---
device_id | The Appliance code (Device ID) of appliance
attribute | "oscillation_angle"
value | "Off"<br/>"30"<br/>"60"<br/>"90"<br/>"120"<br/>"180"<br/>"360"

Name | Description
--- | ---
device_id | The Appliance code (Device ID) of appliance
attribute | "tilting_angle"
value | "Off"<br/>"30"<br/>"60"<br/>"90"<br/>"120"<br/>"180"<br/>"360"<br/>"+60"<br/>"-60"<br/>"40"

Example
```
service: midea_ac_lan.set_attribute
data:
  device_id: XXXXXXXXXXXX
  attribute: power
  value: true
```

```
service: midea_ac_lan.set_attribute
data:
  device_id: XXXXXXXXXXXX
  attribute: oscillation_angle
  value: "90"
```