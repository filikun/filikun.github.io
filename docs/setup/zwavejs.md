---
layout: default
title: 🔗 zwavejs
parent: ⚙️ Setup
nav_order: 43
---
# Zwave JS

## Set clock on thermostats 

```yaml

  service: zwave_js.invoke_cc_api
  data:
    command_class: "129"
    method_name: set
    parameters: >-
      {% set t = now() + timedelta(seconds=30) %} {% set t = t -
      timedelta(seconds=t.second, microseconds=t.microsecond) %} {{ [t.hour,
      t.minute, t.weekday()+1] }}
  target:
    device_id:
      - YOUR_DEVICE_ID

```

[Device-Availability](https://www.zigbee2mqtt.io/guide/configuration/device-availability.html#availability-advanced-configuration)
