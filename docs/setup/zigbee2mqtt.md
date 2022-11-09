---
layout: default
title: 🔗 zigbee2mqtt
parent: ⚙️ Setup
nav_order: 42
---
# Zigbee2MQTT

## Availability

Setting availability to "Availability (simple)" will allow Z2M to report if a device is offline. If this setting is not on HA will just stop reporting the state for devices that for example lose power, so if they where on they will still look like they are on in HA. This setting will make it unavaiable in HA.

[Device-Availability](https://www.zigbee2mqtt.io/guide/configuration/device-availability.html#availability-advanced-configuration)